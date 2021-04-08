# Yankees by the Numbers
This dataset contains famous numbers relevant to the history of the New York Yankees/Highlanders.

## How do I use this?
Grab the CSV file.  For the number you want, take that line of the CSV file.  One or more comma-separated and properly-delimited facts will be available for you to use.

### Sample PHP code
```php
// Open the file and use CSV parsing mode.
$file = new SplFileObject('facts.csv', 'r');
$file->setFlags(SplFileObject::READ_CSV | SplFileObject::DROP_NEW_LINE);

// Get the desired line number.
// Note that SplFileObject::seek() uses zero-based indexing!
$file->seek($NUMBER_YOU_WANT - 1);

// Get an array full of zero or more facts.
$facts = $file->current();

// Close the file.
$file = null;
```

### Sample PowerShell code
```powershell
(Get-Content -Path 'facts.csv' -TotalCount $NUMBER_YOU_WANT)[-1]
```

## Did **you** use this?
Yes.  Visit [https://TightenThisShitUp.com](https://tightenthisshitup.com) for a live demo.  The number it pulls for facts is the number of men left on base by the 2021 Yankees.  (Not good enough?  There is an "easteregg" parameter to really see it in action.  Don't abuse my bandwidth without making a donation.)

## *May* I use this?
This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

![CC-BY-4.0](https://i.creativecommons.org/l/by/4.0/88x31.png)

## Where did you get this data?
Mostly Wikipedia, Baseball Reference, and a bunch of other places.  No unverified research went into the creation of this dataset.

## Hey, you missed something; you have a typo; or you got something wrong.
Submit a pull request.  Please cite your source, too.

## You know, you can do a lot better than a giant CSV file.
I know.  I'll think about other formats.  Ideally, you would want to take this file and load it into a proper database.  Parsing this millions-line-long CSV file is going to be an exercise in futility.
