
namespace :greeting do
  desc 'outputs hello to the terminal'
    task :hello do
      puts "hello from Rake!"
    end

    desc 'outputs hola to the terminal'
    task :hola do
      puts "hola de Rake!"
    end
  end

# One common pattern you'll soon become familiar with is the pattern of
# writing code that creates database tables and then "migrating" that code using a rake task
task :environment do
  require_relative './config/environment'
end

namespace :db do
  desc 'migrate changes to the database'
  task migrate: :environment do
    Student.create_table
  end
  # "seeding" our database with some placeholder data.
  desc 'seed the database with some dummy data'
  task seed: :environment do
    require_relative './db/seeds'
  end
end

# task that starts up the Pry console
desc 'drop into the Pry console'
task console: :environment do
  Pry.start
end
