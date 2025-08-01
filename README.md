# Biometric XML Generator

This script checks for duplicate biometric and biographic data using a YAML database and generates a formatted XML result.

## Features

- Checks for duplicate face and fingerprint hashes, as well as biographic (name and DOB) matches.
- Stores new entries if not detected as duplicates.
- Outputs a pretty-printed XML result to `biometric_result.xml`.

## Usage

1. **Install dependencies:**
   ```sh
   pip install pyyaml
   ```

2. **Run the script:**
   ```sh
   python biometric_xmlgenerator.py
   ```

3. **Customize input:**
   Edit the following section in [`biometric_xmlgenerator.py`](xml/biometric_xmlgenerator.py) to change the input data:
   ```python
   xml_result = checker.check_and_store(
       name="Jane Doe",
       dob="1991-02-02",
       face_hash="face123456",
       finger_hash="finger654321"
   )
   ```

4. **Check the output:**
   - The XML result will be printed to the console.
   - The result is also saved to `biometric_result.xml` in the same directory.

## Database

- The script uses a YAML file (`biometric_db.yaml`) to store and check biometric records.
- The file is created automatically if it does not exist.

## Example Output

```xml
<BiometricTransactionResult>
  <TransactionTimestamp>2025-08-01T06:56:46.879826Z</TransactionTimestamp>
  <BiographicData>Jane Doe, DOB: 1991-02-02</BiographicData>
  <FaceDuplicationStatus>NOT_DETECTED</FaceDuplicationStatus>
  <FingerDuplicationStatus>NOT_DETECTED</FingerDuplicationStatus>
  <BiographicDuplicationStatus>NOT_DETECTED</BiographicDuplicationStatus>
  <MatchStatus>STORED</MatchStatus>
</BiometricTransactionResult>
```

## License

MIT License
