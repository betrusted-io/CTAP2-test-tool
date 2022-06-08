## Precursor

| Category    |   Passed |   Total |
|-------------|----------|---------|
| All         |       71 |      74 |
| Client PIN  |       38 |      40 |
| FIDO 2.1    |        7 |       8 |
| HMAC Secret |        1 |       1 |

### Failed tests:

* Tests if PIN auth attempts are blocked correctly.
  * Getting the auth token failed after replugging an auth block.
  * GetAuthToken failed.
  * The failing error code is `CTAP2_ERR_PIN_AUTH_BLOCKED`.
* Tests if PINs are blocked correctly.
  * PIN retries did not decrement correctly.
  * Expected error code `CTAP2_ERR_PIN_INVALID`, got `CTAP2_ERR_PIN_AUTH_BLOCKED`.
* Tests if Reset requirements are enforced.
  * Reset was allowed 10 seconds after plugging in.
  * Expected error code `CTAP2_ERR_USER_ACTION_TIMEOUT`, got `CTAP2_ERR_NOT_ALLOWED`.
  * A prompt was sent unexpectedly.
  * Expected error code `CTAP2_ERR_NOT_ALLOWED`, got `CTAP2_OK`.

### Device capabilities

* HID
  * CBOR: True
  * MSG : True
  * WINK: True
* Versions
  * U2F_V2
  * FIDO_2_0
  * FIDO_2_1_PRE
* Options
  * up
  * rk
  * clientPin
* Extensions
  * hmac-secret
* All counters were strictly increasing, but not necessarily incremented by 1.

### Device information

* Serial number: 4cb5ce5458c85c
* Manufacturer: Kosagi
* Vendor ID : 0x1209
* Product ID: 0x0001
* AAGUID: 000102030405060708090a0b0c0d0e0f
