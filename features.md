## Important Features in Your Dataset
## Here are the key columns you need to understand:

### Basic Transaction Info
**block_id:** The block in which the transaction was recorded. A block is like a batch of transactions.

**size:** The size of the transaction in bytes.

**weight:** A measure of how much space the transaction takes in the blockchain.

**version:** The version of the Bitcoin transaction format.

**lock_time:** A time constraint that prevents the transaction from being spent until a certain block/time.

### Money-Related Features
**balance:** The balance of the sender after the transaction.

**amount:** The amount of Bitcoin transferred in the transaction.

**input_total & output_total:** The total amount of Bitcoin received and sent in the transaction.

**fee:** The transaction fee paid to miners (higher fees = faster confirmation).

### Special Features
**is_coinbase:** Whether the transaction is a mining reward (1 = Yes, 0 = No).

**has_witness:** Whether the transaction uses SegWit (a Bitcoin upgrade).

### Fraud Detection Column
**label:** This column likely indicates whether a transaction is fraudulent (e.g., 1 = fraud, 0 = normal).