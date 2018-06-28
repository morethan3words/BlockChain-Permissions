# BlockChain-Permissions
Managed Permissions Across Multiple Networks
## Team Zelda/Mother May I
Who we are: Will Gray - Data/Intelligence Analyst, Connor Bulakites - Associate Data Scientist, Jessica Gonzalez - Digital Network Intelligence Analyst (ACOS) 

## Managed Permissions in the Blockchain:
The basics: 
This is done by adding/removing permissions on the blockchain.
The blockchain would make this use case easier to manage perhaps more secure and auditable. Two groups – Authorities and Users.

### Advantages: 
Compared to other distributed ledgers, the Blockchain can be used securely across multiple entities and organizations. It will also be easier to detect if/when an unauthorized user attempts to tamper with the permissions on the chain.

### Disadvantages: 
Scalability - However, this is addressed by limiting the number of transactions that need to take place on the chain

### Database holding our ledger: 
Key-value store which is a dictionary holding the values for our chain. The blocks in our permissions chain would look like this:
#### “gov grants cert_a to will": 1
#### "key grants cert_b to will": 2
#### "gov revokes cert_a from will": 3
#### "gov grants cert_a to jessica:" 4
#### ..
#### ..
#### ..

### Then, in order to figure out if Will has cert_a and cert_b, one would filter the database to all values which have the keys “gov grants cert_a to will”, “key grants cert_b to will”, “gov revokes cert_a from will”, “key revokes cert_b from will” 

### Which would then return this subset of entries:
#### "gov grants cert_a to will": 1
#### "key grants cert_b to will": 2
#### "gov revokes cert_a from will": 3

#### Which would tell you that Will has cert_b but not cert_a as it has been revoked. Additionally, theoretically these values would further be hashed for increased encryption and security. That way if an unauthorized user were to gain access to the chain, they would not be able to tell exactly which certs and permissions have or have not been granted to Will. Nor would they be able to alter those permissions. 

#### Further, if one were to implement/store Javascript in the chain, a key could be added to the employee’s name and a value would be added to signify their clearances/permissions. Thus one would only need to look up the employee’s last transaction in the chain to verify their clearances. 

