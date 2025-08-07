# Biometric XML Generator

This repository contains a simple Python script for duplicate checking and data storage using biometric and biographic data. The checker evaluates face and fingerprint hashes, as well as name and date of birth, and generates a formatted XML result. Data is stored in a YAML file for easy management and demonstration.

## Getting Started

### Prerequisites

Make sure you have the following installed:
- **Python 3.7+** (for running the script)
- **pip** (Python package manager)

### Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/biometric-xml-generator.git
cd biometric-xml-generator
```

Install dependencies:

```bash
pip install pyyaml
```

## Usage

Edit the input data in the script as needed:

```python
xml_result = checker.check_and_store(
    name="Jane Doe",
    dob="1991-02-02",
    face_hash="face123456",
    finger_hash="finger654321"
)
```

Run the script:

```bash
python biometric_xmlgenerator.py
```

The XML result will be printed to the console and saved as `biometric_result.xml` in the current directory.

### How It Works

- The script checks for duplicate entries based on:
  - Name and date of birth (biographic match)
  - Face hash
  - Fingerprint hash
- If a duplicate is detected, the result is flagged and the match status is updated.
- If no duplicate is found, the entry is stored in `biometric_db.yaml`.
- The result of each check is output as a formatted XML file.

## Example XML Output

```xml
<BiometricTransactionResult>
  <TransactionTimestamp>2025-08-07T12:34:56.789012Z</TransactionTimestamp>
  <BiographicData>Jane Doe, DOB: 1991-02-02</BiographicData>
  <FaceDuplicationStatus>NOT_DETECTED</FaceDuplicationStatus>
  <FingerDuplicationStatus>NOT_DETECTED</FingerDuplicationStatus>
  <BiographicDuplicationStatus>NOT_DETECTED</BiographicDuplicationStatus>
  <MatchStatus>STORED</MatchStatus>
  <Flagged>NO</Flagged>
</BiometricTransactionResult>
```

## Data Storage

- All biometric and biographic data is stored in a YAML file (`biometric_db.yaml`).
- The file is created automatically if it does not exist.

## Logging

- The script prints the XML result to the console.
- The XML result is also saved to `biometric_result.xml`.

## Configuration

- You can change the database file path by passing a different filename to `BiometricChecker(database_path="your_db.yaml")`.

## Built With

* [Python 3](https://www.python.org/)
* [PyYAML](https://pyyaml.org/)
* [xml.etree.ElementTree](https://docs.python.org/3/library/xml.etree.elementtree.html)

## Authors

Your Name - _Initial work_ - [yourusername](https://github.com/yourusername)

## License

Distributed under the MIT License. See `LICENSE` for more information.

## Acknowledgements

- Inspired by real-world biometric deduplication systems.
- Uses open-source Python libraries for YAML and XML processing.
