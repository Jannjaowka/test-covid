# test-covid
input {
  file {
    path => "<path>/covid-19 test.csv"
    start_position => "beginning"
    sincedb_path => "/dev/null"
  }
 }
 filter {
  csv {
      separator => ","
      columns => ["Entity","Code","Date","New tests","Lat","Long"]
  }
  }
  output {
     elasticsearch {
      hosts =>"http://localhost:8888"
      index => "English"
     }
  stdout{}
  }

