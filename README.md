**Download the current data catalog (beta!) by right-clicking on the below link and selecting "Save Link As":**

**https://raw.github.com/codeforamerica/healthdatagov-csv-metadata/master/healthdatagov_metadata_catalog_beta_060213.csv**



healthdatagov-csv-metadata
=====

This is a Ruby script (and quasi-library) that creates an Excel-readable metadata catalog for data sets on [HealthData.gov](http://www.healthdata.gov).

It's super hacky right now, but seems to get the job done! And it even has TESTS!

Installation / Usage
----

This script requires Ruby 1.9.3, RubyGems, and bundler. Installation instructions can be found at: (http://www.ruby-lang.org/en/downloads/)[http://www.ruby-lang.org/en/downloads/]

To create a metadata catalog, run the following commands in the project directory:

```shell
bundle install
ruby create_csv_script.rb
```

You'll then have a file named *healthdatagov_metadata_catalog.csv* in the project directory representing metadata for all the datasets available on HealthData.gov.

Code Overview
----

* `healthdatagov_metadata_catalog_beta_060213.csv` is the first version of the data catalog
* `create_csv_script.rb` is a simple script that uses the library to create a csv.
* `lib/health_data_catalog.rb` is the workhorse library, with a bunch of functions to break down the task of getting data, processing it, and making a catalog

Note: because this is a very-beta version, it uses VCR to save metadata locally. If you are using this to routinely create a catalog, you will want to be sure to delete the `vcr_cassettes` directory that will be created before running the script again (this flushes all the old data, and will get all new data from the API).

Other Info
----

This was built by Dave Guarino ([@daguar on Github](https://github.com/daguar), [@allafarce on Twitter](https://www.twitter.com/allafarce)) for the National Day of Civic Hacking 2013.

See LICENSE.md for license (BSD)

