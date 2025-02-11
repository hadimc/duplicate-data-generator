# duplicate-data-generator
This script will create duplicates in known quantities to test record linkage (e.g. MDM) systems.  To further test the fuzzy matching of your record linkage system, the script can trasposition and mistype duplicated columns.  

Note: this script is only a thin wrapper over the existing [Faker](https://github.com/joke2k/faker) library.

## Installation
1. Install Python 3+
2. Download the repository
3. Install the referenced modules with: pip install -r requirements.txt

## Usage
python duplicate_data_generator.py --config dup_data_config.json --output output.xlsx

## Config File Settings
### total_row_cnt
The total number of rows you would like produce
### duplication_rate
The known duplication rate of the records to produce
### localization
See [here](https://faker.readthedocs.io/en/master/locales.html) for a list of possible values
### columns
#### name
The name of the column written to the Excel sheet
#### type
Supported types are: "first_name","last_name", "street_address", "secondary_address", "city", "state", "postcode", "current_country", "phone_number", "email", "date_of_birth"
#### transposition_chars
The number of characeters to transposition (e.g. switch) within the cell of a column
#### mistype_chars
The number of characeters to mistype within the cell of a column
#### deleted_words
How many (space-seprated) words are deleted from the cell of a column 
#### initial_chars
The maximum number of initial characters that are kept from the cell of a column (the number is chosen at random)


