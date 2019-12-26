require 'csv'

namespace :verge_sense_coding_exercise do

  desc 'Given an array of integers, write a function to sort the integers in the array
        while preserving the relative ordering of the negative and positive integers
        respectively.'
  task :answer_question_1, [:integer_array] do |t, args|
    starting_array = []
    starting_array = args.integer_array.split(' ').map{ |s| s.to_i }
    puts starting_array
    if starting_array.empty?
      puts "array connot be empty"
      puts "usage: rake verge_sense_coding_exercise:answer_question_1['3 1 -7 -9 -10 2']"
      next
    end

    puts "starting array: #{starting_array}"
    positive_array = []
    negative_array = []
    starting_array.each do |i|
      # we will assume 0 is a positive number
      if i >= 0
        positive_array << i
      else
        negative_array << i
      end
    end

    puts "result is: #{negative_array + positive_array}"
  end

  desc "usage: rake verge_sense_coding_exercise:answer_question_2['VS_Coding_Exercise_Data.csv']"
  task :answer_question_2, [:csv_file] do |t, args|
    starting_array = args.csv_file
    parsed_file = CSV.read(args.csv_file, 'rb:UTF-8', force_quotes: true, headers: false)
    sensor_data = {}
    parsed_file.each do |row|
      sensor_timestamp = row[0]
      sensor_name = row[1]
      sensor_value = row[2]
      next if sensor_name.nil? || sensor_timestamp.nil? || sensor_value.nil?

      if !sensor_value.nil? && (sensor_value.to_i > sensor_data[sensor_name.to_sym].to_i)
        sensor_data[sensor_name.to_sym] = sensor_value
      end
    end
    puts sensor_data
    sensor_data
  end

  task :answer_question_3 do |t, args|
    puts "see verge_sense_project.pdf"
  end

end
