DATA = ../../data 
TEMP = ../../gen/temp

all: $(TEMP)/calendar_cleaned.csv $(TEMP)/listings_cleaned.csv $(TEMP)/airbnb_merged.csv


../../data/calendar.csv ../../data/listings.csv: download_data.R
	R --vanilla < download_data.R

$(TEMP)/calendar_cleaned.csv $(TEMP)/listings_cleaned.csv: clean_data.R ../../data/calendar.csv ../../data/listings.csv
	R --vanilla < clean_data.R

$(TEMP)/airbnb_merged.csv: merge_data.R $(TEMP)/calendar_cleaned.csv $(TEMP)/listings_cleaned.csv
	R --vanilla < merge_data.R
