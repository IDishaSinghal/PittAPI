# Pitt API

![Build Status](https://img.shields.io/github/actions/workflow/status/pittcsc/PittAPI/autotest.yml?branch=dev)
![License](https://img.shields.io/badge/license-GPLv2-blue.svg)
![Python Version](https://img.shields.io/badge/python-%3E%3D%203.9-green.svg)
![PyPI](https://img.shields.io/pypi/v/pittapi.svg)

The Pitt API is an unofficial Python API made by Ritwik Gupta at the University of Pittsburgh in an effort to get more open data from Pitt.

## Usage examples

```python
from pittapi import course, dining, lab, laundry, library, news, people, shuttle, textbook

### Courses
# Returns a dictionary of all courses for a given subject
cs_subject = course.get_subject_courses(subject='CS')
courses_dict = cs_subject.courses

# Returns a list of sections of a course during a given term
cs_course = course.get_course_details(term='2244', subject='CS', course='1501')
section_list = cs_course.sections

### Textbook
# Returns a list of dictionaries containing textbooks for a class
# Term number comes from pitt.verbacompare.com
small_dict = textbook.get_textbook(term="3150", department="CS", course="445", instructor="RAMIREZ")

### Library
# Returns a dictionary containing results from query
big_dict = library.get_documents(query="computer")

### News
# Returns a list of dictionaries containing news from main news feed
medium_dict = news.get_news()

### Laundry
# Returns a dictionary with number of washers and dryers in use vs.
# total washers and dryers in building
small_dict = laundry.get_status_simple(building_name="TOWERS")

### Computer Lab
# Returns a dictionary with status of the lab and number of open machines
small_dict = lab.get_status(lab_name="ALUMNI")

### Shuttle
# Returns a list of dictionaries containing routes of shuttles
big_dict = shuttle.get_routes()

### People
# Returns a list of people based on the query
list_of_peeps = people.get_person(query="Smith")

### Dining
# Returns a dictionary of dictionaries containing each dining location with its
# name and open/closed status
medium_dict = dining.get_locations()
# Returns a dictionary of a dining location with its hours for a given day
hours = dining.get_location_hours("The Eatery", datetime.datetime(2024, 4, 12))
```
## Installation
You can install the PittAPI package via pip:
```bash
pip install pittapi

You can also install it from the GitHub repository:
pip install git+https://github.com/Pitt-CSC/PittAPI.git

If you want to install it for development purposes, use this:
pip install -e .[dev]

This way, it's more complete and gives users options for different installation

```
## Local Setup

1. Install Python 3.12 or higher from the official Python website (https://www.python.org/downloads/).
2. Install `pipenv` by running the following command:

```bash
pip install pipenv

Navigate to the project directory and run the following commands to set up the virtual environment:
pipenv install  # This will install the required dependencies
pipenv shell    # This will activate the virtual environment

## Contributing

We welcome contributions to the Pitt API! If you would like to contribute to the project, please follow our [contributing guidelines](/CONTRIBUTING.md) to get started.

You can contribute by:

- Reporting bugs
- Submitting pull requests for bug fixes or new features
- Improving documentation

## License

This project is licensed under the terms of the [GPLv2 license](/LICENSE).
