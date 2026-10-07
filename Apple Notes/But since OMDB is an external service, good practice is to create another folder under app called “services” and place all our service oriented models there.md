---
apple-notes-id: 73CEACF9-1176-4BA0-B5DD-3F99A4971DD7
---
*def* get_data_by_title(title)
    token = Rails.application.credentials.omdb\[:api_key\]
    base_url = 'http://www.omdbapi.com/?apikey='
    res = HTTP.get(base_url+token+"&t=#{title}").to_s
    parse_resp = JSON.parse(res)
  *end*


  *def* get_data_by_id(id)
    token = Rails.application.credentials.omdb\[:api_key\]
    base_url = 'http://www.omdbapi.com/?apikey='
    res = HTTP.get(base_url+token+"&i=#{id}").to_s
    parse_resp = JSON.parse(res)  
  *end*


gem 'json', '~> 1.8', '>= 1.8.3'
gem "http"