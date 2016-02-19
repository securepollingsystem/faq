## Frequently Asked Questions about the Secure Polling System ##

### Can you describe in a few simple sentences how your online-voting-works? ###

Voters post their political opinions on the internet with a cryptographic signature traceable to the Registrar of Voters.  They compose original lines and/or copy popular lines from recent tallies to express whatever they desire.  Anyone can read and verify the signatures on these postings, and use their computer to tally up the popular lines into meaningful numbers.  The cryptography behind their signature allows verification of Voter status while preserving anonymity, even from the Registrar.

### Can you describe it in a more detailed way? ###

Eligible Voters are allowed to have a blinded cryptographic public key signed by the Registrar, who signs with a key which expires 12 months later.  Voters can post political opinions as a list of statements separated by newlines, which is signed using their private key, and posted along the Registrar’s signature of their public key (and their own public key).

Now this signed list of opinions is posted anywhere on the internet, and anyone seeing that list can verify its integrity and traceability to the Registrar, by verifying the signature with the presented public key, and verifying the presented signature of that key with the Registrar’s public key.

Anyone can use their computer to tally all the identical lines from all the verified postings, and get a list of the most popular lines that people espouse.  Voters then add popular lines to their own profile if they match with their political opinions, which makes it easier for anyone to quantify public opinion.  Anyone can create a new line simply by adding it to their signed post, and hope that others agree with the wording enough to copy it into their own postings.

By using a “Blind Signature” process, Voters do not reveal their public key the Registrar when it needs to be signed.  This means that even the Registrar cannot correlate their legal name or identity with the opinions they post using their signed key.

### What’s the difference to other online-voting-tools out there? ###

Other online voting tools invariably fall into the “multiple choice” category of voting, which simply transfers the fraud and disenfranchisement to the process of choosing the questions.  They are also so heavy on math and complex cryptography that participants are no more confident than the old ballot box that their vote means anything.  With the Secure Polling System, Voters can see every part of the process, and they can count the votes - even their own.

### How do you prevent fake accounts in order to get a disproportionate amount of power? ###

Only the Registrar has the power to grant the ability to participate, by signing a Voter’s (blinded) public key.  The Registrar works from the publicly available Voter rolls, marking off those Voters whose keys have been signed, so no one can be signed twice in the same period.  The public can inspect this list and if the Registrar has been giving out extra signatures, there will be more public profiles than the number of names on the list, indicating that fraud has been committed by the registrar.

The Registrar signs with a new key every month, which is declared to expire 12 months later.  Voters are allowed a new signature only after their previous signature has expired, based on the records maintained by the Registrar.

### How doesn’t the Registrar know who voted how? ###

Before the Voter goes to the Registrar, their client software has guided them to generate a new key pair, and to make a “blinded” version of their public key.  The Voter only presents this “blinded” public key to the Registrar for signing, so even if the Registrar keeps a copy of the data, they cannot correlate it to the public key that the voter will use for posting publicly.

When the Voter returns home from the Registrar, they “unblind” the signature made by the Registrar which yields a signature of their “unblinded” public key.  They can present this signature as proof that their public key belongs to an eligible Voter.

Q: What does "key blinding" mean / how does it work?
A: Key Blinding is the process by which the voter's public key is made unrecognizable, before it is presented to the Registrar to be signed.  It works because the voter never shows their unblinded public key to the registrar, so the registrar can't connect their identity with the postings they will make online.  How exactly it works is a cryptographic miracle, and is beyond the scope of this FAQ.

Q: How do you guarantee anonymity of vote and verifiability at the same time?
A: The Voter only needs to reveal her or his identity to the Registrar, once per year at the time of signing the Voter’s blinded public key.  The blinding guarantees that even the Registrar can’t associate the person with his or her voting.

### How do you guarantee anonymity of vote and verifiability at the same time?  ###

The Voter only needs to reveal her or his identity to the Registrar, once per year at the time of signing the Voter’s blinded public key.  The blinding guarantees that even the Registrar can’t associate the person with his or her voting.

Verifiability is possible because every posting of political opinions to be counted by the Secure Polling System must be signed with a cryptographic key, and presented with proof that the key was signed by the Registrar.  Anyone counting the votes (and anyone can do so) can independantly verify the Registrar’s signature using the Registrar’s public key as posted on an official government website, and even checked against a key fingerprint printed on the Registrar’s business card.

### What if any part of the system or your computer gets hacked in a way that they manipulate your vote? ###

If an eligible Voter reveals the passphrase to his or her cryptographic private key which they use for Secure Polling System, the result is the same whether they did so voluntarily or accidentally.

If the Voter becomes aware that their private key is being accessed by someone else, they can post a signed statement revoking the trust to their public key, which will tell people counting profiles to ignore all profiles coming from that key.  When the signature by the Registrar expires (in less than a year), the Voter can use a new key and have it signed by the Registrar.  And this time they will be more careful with their private key and passphrase.

### How does the tallying work? ###

Software made for this purpose is executed by anyone wanting to take a tally.  The software reads postings placed by Voters, some of which are accompanied by links to other postings placed by Voters.  When the software finds all the signed posts, possibly with the help of a peer-to-peer notoriety system, the verification and tallying begin.

The verification stage checks each posting against the public keys of the Registrar, and groups postings by the voters’ key fingerprint, in case a person’s postings are found in multiple places on the internet.  This way a single person won’t be counted multiple times.

The counting software considers each unique line of each voters’ verified postings as a separate item.  At the end of the count, the computer presents a list of the most popular items which were present (identical text) in the most Voters’ postings.  Anyone viewing these results can immediately see that, for example, 77% of postings found in this count contained the item “Increase taxes on fossil fuels by 25 percent” and make use of the information accordingly.

Since anyone can do a count and get the same results, the information is de facto.

### What if any part of the system or your computer gets hacked in a way that they can see how you vote? ###

The whole point of this system is to make your political opinions known, in the context of your status as a registered Voter.  Only the Registrar has to see your legal name when your key is being signed, and the “blinding” process prevents them from seeing your cryptographic key.

The only secret aspect of this information (besides your password to your private key) is your identity.  If your computer gets hacked and all of your information is revealed to unauthorized parties, those people knowing your political opinions will be the least of your problems.

### What if someone forces you or gives you money to vote in a certain way? ###

Vote-buying is illegal, as are threats or blackmail.  If enough people report to the District Attorney that a person is attempting to buy votes, the D.A. will charge that person with a crime and summon people who were solicited to testify against the accused at trial.  In order for a person to effectively influence a voting topic, they would have to acquire far more than enough votes to assure their prosecution.

### Can I verify if my voting was tallied correctly? ###

You can check any tally posted on the internet for a list of cryptographic key fingerprints included in their poll.  If your fingerprint is present in the list, you know that they were aware of your posting.
The only way to be sure your vote is actually counted is to count it yourself, or look at a count done by someone you trust.  If multiple competing news sources and political entities agree on the breakdown of tallies, it is evidence that the entire body of valid postings is included.

### What if you forget your passphrase? ###

The purpose of a passphrase is to prevent unauthorized use of your cryptographic key.  If you forget it, you will be unable to change your posting until the signature of your key expires, less than a year later.  At that time, you can create a new key and use a new passphrase, which you will remember to write down this time.

### What if they hack your account? ###

There is no account with this system, only cryptographic keys used by Voters to prove authenticity of their postings.  There is no outside agency involved in cryptographic keys other than the laws of mathematics.  If your private key and passphrase are leaked to an unauthorized party, you can post a revocation of your key, and those who are counting postings will not count your key as valid.

The only type of “account” used with this system is your legal identity, as shown to the Registrar with your government-issued ID card or similar papers.  Anyone presenting fraudulent documents pretending to be you is committing the crime of identity fraud and will be caught.
