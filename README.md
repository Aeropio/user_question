
* Ruby version - ruby 2.5.3p105

* Database creation - Use gem sqlite3 in local and change the database.yml file 
run bundle install 
change database.yml to 

default: &default
  adapter: sqlite3
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  timeout: 5000

development:
  <<: *default
  database: db/development.sqlite3
  <<: *default
  database: db/test.sqlite3

production:
  <<: *default
  database: db/production.sqlite3
##################################

migrate the db using rake db:migrate
run server using rails s
go to http://localhost:3000/users/sign_in
