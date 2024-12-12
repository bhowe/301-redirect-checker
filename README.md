301 Redirect Checker
A PHP script to verify 301 redirects and their destinations from a CSV file. This tool helps webmasters and SEO professionals verify that their redirects are working correctly and leading to valid pages.
Features

Validates 301 redirects from a CSV input file
Verifies that destination URLs exist (not 404)
Checks if actual redirect destinations match expected URLs
Generates detailed reports with success/failure information
Handles trailing slashes in URL comparisons
Validates URL formats before processing
Provides specific error messages for different types of failures

Requirements

PHP 7.0 or higher
PHP cURL extension enabled
Read permissions for CSV files

Installation

Clone this repository:

bashCopygit clone https://github.com/yourusername/301-redirect-checker.git
cd 301-redirect-checker

Ensure you have PHP and the cURL extension installed:

bashCopyphp -m | grep curl
Usage

Create a CSV file with your redirects (e.g., redirects.csv):

csvCopysource_url,destination_url
https://oldsite.com/page1,https://newsite.com/page1
https://oldsite.com/page2,https://newsite.com/page2

Run the script:

bashCopyphp redirect-checker.php
CSV Format
The CSV file should contain two columns:

First column: Source URLs to check
Second column: Expected destination URLs

Example:
csvCopysource_url,destination_url
https://oldsite.com/page1,https://newsite.com/page1
https://oldsite.com/page2,https://newsite.com/page2
Output
The script generates a detailed report showing:

Each URL checked
Expected and actual destinations
Initial redirect status code
Destination page status code
Success/failure status
Specific error messages if any issues are found
Summary of total checks and success/failure counts

Example output:
Copy301 Redirect Verification Report
==============================

Source URL: https://oldsite.com/page1
Expected Destination: https://newsite.com/page1
Actual Destination: https://newsite.com/page1
Initial Status Code: 301
Destination Status Code: 200
Match: ✓ YES
----------------------------------------

Summary:
Total checks: 1
Successful redirects: 1
Failed redirects: 0
Error Handling
The script checks for and reports the following issues:

Non-301 redirect status codes
Mismatched destination URLs
404 errors at destination URLs
Unreachable destinations
Invalid URL formats in CSV
Missing or unreadable CSV files

Contributing

Fork the repository
Create a feature branch (git checkout -b feature/improvement)
Commit your changes (git commit -am 'Add new feature')
Push to the branch (git push origin feature/improvement)
Create a Pull Request

License
This project is licensed under the MIT License - see the LICENSE file for details.
Support
For issues, questions, or contributions, please open an issue on the GitHub repository.


Acknowledgments

Thanks to the PHP community for cURL documentation and examples
Inspired by the need for better redirect validation tools
