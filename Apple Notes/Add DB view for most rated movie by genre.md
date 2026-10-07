---
apple-notes-id: B1510829-AE8A-4D36-ABAC-829E037D352C
---
Create this DB view to get  most rated movie by genre


 it 'returns most rated movie by genre' do
    movies = create_list(:movie, 10)
    ratings = movies.each do |movie|
      create(:rating, movie: movie)
    end
    raise ratings.inspect

  end