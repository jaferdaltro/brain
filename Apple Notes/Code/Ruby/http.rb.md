---
apple-notes-id: D20A2E0E-D638-454B-8C30-FAC1926824A5
---
require 'json'
require 'faraday'

class BaseHttp
  DEFAULT_OPTIONS = { headers: {} }.freeze
  def initialize(options = {})
    options = DEFAULT_OPTIONS.merge(options)
    base_headers = {
      accept: 'application/json',
      user_agent: 'Billimatic App',
    }.merge(options\[:headers\])
    http_service = options\[:http_service\]
    headers = base_headers.merge({ content_type: 'application/json' })

    @http = http_service || Faraday.new(url: @base_url, headers: headers) do |faraday|
      faraday.response :logger, ::Logger.new(STDOUT), bodies: true
    end

    @http_multipart = http_service ||
      Faraday.new(url: @base_url, headers: base_headers) do |faraday|
        faraday.response :logger, ::Logger.new(STDOUT), bodies: true
        faraday.request :multipart
      end
  end

  def get(url)
    response = @http.get(url)

    handle_response(response)
  end

  def delete(url)
    response = @http.delete(url)

    handle_response(response)
  end

  def post(url, data)
    data = data.to_json if data.class == Hash
    response = @http.post(url, data)

    handle_response(response)
  end

  def upload_file(url, data)
    response = @http_multipart.post(url, data)

    handle_response(response)
  end

  def build_file(path, content_type)
    Faraday::UploadIO.new(path, content_type)
  end

  def method_missing(m, *args, &block)
    puts "There's no method called #{m}"
  end

  private

  def handle_response(response)
    parsed_body = parse_body(response.body)

    return { "error" => parsed_body } if (400..599).include?(response.status)

    parsed_body
  end

  def parse_body(body)
    JSON.parse(body)
  rescue
    body
  end
end