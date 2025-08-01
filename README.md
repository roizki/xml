Biometric XML Generator

A Python script to check for duplicate biometric and biographic data, store new entries, and generate a formatted XML result.

## Features

- Checks for duplicate face and fingerprint hashes, as well as biographic (name and DOB) matches.
- Stores new entries in a YAML database (`biometric_db.yaml`).
- Outputs a pretty-printed XML result to `biometric_result.xml`.

## Requirements

- Python 3.x
- [PyYAML](https://pyyaml.org/)

Install dependencies:
```sh
pip install pyyaml
```

## Usage

1. **Edit the input data** in the script:
    ```python
    xml_result = checker.check_and_store(
        name="Jane Doe",
        dob="1991-02-02",
        face_hash="face123456",
        finger_hash="finger654321"
    )
    ```

2. **Run the script:**
    ```sh
    python biometric_xmlgenerator.py
    ```

3. **Output:**
    - The XML result will be printed to the console.
    - The result is also saved to `biometric_result.xml`.

## Example XML Output

```xml
<BiometricTransactionResult>
  <TransactionTimestamp>2025-08-01T06:56:46.879826Z</TransactionTimestamp>
  <BiographicData>Jane Doe, DOB: 1991-02-02</BiographicData>
  <FaceDuplicationStatus>NOT_DETECTED</FaceDuplicationStatus>
  <FingerDuplicationStatus>NOT_DETECTED</FingerDuplicationStatus>
  <BiographicDuplicationStatus>NOT_DETECTED</BiographicDuplicationStatus>
  <MatchStatus>STORED</MatchStatus>
  <Flagged>NO</Flagged>
</BiometricTransactionResult>
```

## Database

- The script uses a YAML file (`biometric_db.yaml`) to store and check biometric records.
- The file is created automatically if it does not exist.

## License

MIT License
