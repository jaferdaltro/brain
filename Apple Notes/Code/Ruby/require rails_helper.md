---
apple-notes-id: EA111395-56D7-4853-BA4D-E2DA0CA01877
---
RSpec.describe LoansController do

  context "GET /loans/:id" do

    let!(:loan) { create(:loan) }
    let(:url) { "/loans/#{loan.id}" }

    it 'return requested loan' do
      get url
      expected_loan = loan.as_json(only: %i(id pmt))
      expect(body_json\['loan'\]).to expected_loan
    end 

    # describe "GET show" do
    #   it do
    #     get :show, params: { id: 1 }
    #     param = JSON.parse(response.body).with_indifferent_access
    #     expect(param\[:loan\]\[:id\]).to(eq(1))
    #   end
    # end

  end

  # describe "POST show" do
  #   it do
  #     post :create
  #     param = JSON.parse(response.body).with_indifferent_access
  #     expect(param\[:loan\]\[:id\]).to(eq(2))
  #   end
  # end
end