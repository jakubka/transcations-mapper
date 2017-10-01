# transcations-mapper

Script which maps bank statement export files to a common format suitable to be imported to our excel spredsheet.

## Features

- map Lloyds export csv format to our csv format
- map Monzo export csv format to our csv format
- map TSB export csv format to our csv format

## Prerequisities

Requires Python 3.5 or greater.

## Usage

1. Clone the repo

    `git clone git@github.com:jakubka/transcations-mapper.git`

2. Save exported transactions to `input` folder

    Files have to be named as follow:

    - `lloyds_maja.csv` - will be mapped with LloydsMaja account name
    - `lloyds_master.csv` - will be mapped with LloydsMaster account name
    - `monzo_maja.csv` - will be mapped with MonzoMaja account name
    - `monzo_jakub.csv` - will be mapped with MonzoJakub account name
    - `tsb.csv` - will be mapped with TSBJakub account name
    - `amex.csv` - will be mapped with Amex account name

        This can be generated by:

        1. Download the statement from Amex website in Excel format
        2. Open the file in Excel
        3. Save as.. Choose *CSV UTF-8* format!
        4. Remove rows form the file which do not represent transactions

    Files can be saved to subdirectories, such as `input/statements/amex.csv`.

3. Run

    ```sh
    python3 mapper.py
    ```

    (Python 3.5 or newer required)

    Output will be written to `output.csv`

5. Open new excel workbook and insert data from `output.csv`
    1. Data -> From Text
    2. Set Delimiter=TAB
    3. Set first column as DMY
6. Copy data to the main workbook (paste values)
7. Fill categories
