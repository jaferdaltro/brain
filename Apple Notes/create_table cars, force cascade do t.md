---
apple-notes-id: 26D3D529-C223-4248-8742-D299CF98BFD0
---
t.string "owner", limit: 35, default: "AMT"
    t.string "licence_plate", limit: 8
    t.datetime "created_at", precision: 6, null: false
    t.datetime "updated_at", precision: 6, null: false
    t.string "vtr"
    t.string "brand"
    t.string "model"
  end

  create_table "check_lists", force: :cascade do |t|
    t.datetime "date"
    t.datetime "created_at", precision: 6, null: false
    t.datetime "updated_at", precision: 6, null: false
    t.integer "car_id", null: false
    t.integer "job_id", null: false
    t.boolean "beggin"
    t.boolean "end"
    t.boolean "ready", default: true
    t.index \["car_id"\], name: "index_check_lists_on_car_id"
    t.index \["job_id"\], name: "index_check_lists_on_job_id"
  end

  create_table "items", force: :cascade do |t|
    t.string "description"
    t.datetime "created_at", precision: 6, null: false
    t.datetime "updated_at", precision: 6, null: false
    t.integer "car_id"
  end

  create_table "jobs", force: :cascade do |t|
    t.integer "user_id"
    t.integer "service_id"
    t.datetime "created_at", precision: 6, null: false
    t.datetime "updated_at", precision: 6, null: false
    t.index \["service_id"\], name: "index_jobs_on_service_id"
    t.index \["user_id"\], name: "index_jobs_on_user_id"
  end

  create_table "services", force: :cascade do |t|
    t.datetime "created_at", precision: 6, null: false
    t.datetime "updated_at", precision: 6, null: false
  end

  create_table "truck_drivers", force: :cascade do |t|
    t.string "name"
    t.string "phone"
    t.datetime "created_at", precision: 6, null: false
    t.datetime "updated_at", precision: 6, null: false
  end

  create_table "users", force: :cascade do |t|
    t.string "name"
    t.string "email"
    t.datetime "created_at", precision: 6, null: false
    t.datetime "updated_at", precision: 6, null: false
    t.string "password_digest"
    t.index \["email"\], name: "index_users_on_email", unique: true
  end

  create_table "works", force: :cascade do |t|
    t.integer "truck_driver_id"
    t.integer "service_id"
    t.datetime "created_at", precision: 6, null: false
    t.datetime "updated_at", precision: 6, null: false
    t.index \["service_id"\], name: "index_works_on_service_id"
    t.index \["truck_driver_id"\], name: "index_works_on_truck_driver_id"
  end

end