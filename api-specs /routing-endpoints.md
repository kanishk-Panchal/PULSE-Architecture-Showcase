# PULSE API Routing Specs (Sanitized)

### `POST /api/v1/transaction/execute`
Receives the encrypted payload from the edge terminal via Wi-Fi/NB-IoT.

**Sample Hardware Payload:**
```json
{
  "terminal_id": "PULSE-T3-9942",
  "merchant_vpa": "merchant@icici",
  "customer_mobile": "9876543210",
  "amount_inr": 450.00,
  "biometric_hash_sha256": "e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855"
}
