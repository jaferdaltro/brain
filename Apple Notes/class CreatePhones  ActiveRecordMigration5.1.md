---
apple-notes-id: D451F17B-2500-4125-8482-08FE9A224ADD
---
def change
    create_table :phones do |t|
      t.string :number
      t.references :contact, foreign_key: true

      t.timestamps
    end
  end
end