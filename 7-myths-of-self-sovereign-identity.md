# 7 Myths of Self Sovereign Identity
Taken from Tim Ruff's [October post](https://medium.com/evernym/7-myths-of-self-sovereign-identity-67aea7416b1):

1. Self-sovereign means self-attested.
2. SSI attempts to reduce government’s power over an identity owner.
3. SSI creates a national or “universal ID” credential.
4. SSI gives absolute control over identity.
5. There’s a “main” issuer of credentials.
6. There’s a built-in method of authenticating.
7. User-centric identity is the same as SSI.

### Myth 1: Self-sovereign means self-attested.

#### Third-Party Credentials
In meatspace (real life, compared with cyberspace), to prove something about yourself you must present what others say about you in the form of credentials or other evidence; without this, what you claim about yourself isn’t strongly reliable.

I can claim I went to Harvard, but when a prospective employer needs to know for sure, my claim is no longer sufficient. Saying my credit is great won’t get me a loan, and claiming I’m a pilot won’t get me into the cockpit. I need proof, and it must come from a source that the relying party will trust.

SSI is no different. You can make all the claims you want about yourself, but when a relying party needs to know for sure, you need to show them credentials provably issued by a source the relying party trusts.

#### Self-Attested Credentials
Self-attested verifiable credentials — what you say about yourself — still have their place: they are how you provide your opinion, preference, and most important, consent¹. Opinion, preference, and consent can only reliably come from the identity owner and not from third parties, whereas proof of identity or other attributes are exactly the opposite: they must come from third parties and not the identity owner.

So, to prove Timothy Ruff has given his consent — which only Timothy can give — you must be confident that you’re dealing with the real Timothy Ruff, which is only provable with third-party attestations.

This means that self-attested credentials, including consent, still rely indirectly on third-party credentials. (Unless it’s something like pizza preferences, where who you are doesn’t matter much.)

Bottom line: the foundation of SSI, as with any strong identity system, is third-party issued credentials, not self-attested credentials. SSI supports both, and each type can add value to the other.

### Myth 2: SSI attempts to reduce government’s power over an identity owner.
This myth hearkens back to Kim’s comment, where the term “self-sovereign” could literally be interpreted to mean an individual might somehow become less subject to government. In reality, nothing could be further from the truth. In fact, SSI can actually build a stronger and richer relationship between governments and citizens.

SSI makes possible a private, encrypted, peer-to-peer connection between government and each citizen that can, with mutual consent, be used for powerful mutual authentication (preventing phishing), communication, data sharing, and more. This connection wouldn’t be affected by changes in email address, postal address, phone numbers, and so on. And since both sides of the link would be self-sovereign, either side could terminate it, too.

**From the perspective of government**, the initial function of SSI is straightforward: take existing credentials, whether physical or digital, and begin issuing them cryptographically secure in the form of digital, verifiable credentials. These credentials can then be held independently by the individual, and verified instantly by anyone, anywhere, including government, when presented.

The secondary function of SSI is even more interesting: use the encrypted connection that was created during credential issuance for direct, private, ongoing interaction with the constituent.

**From the perspective of the individual**, we’ve actually had some central features of SSI for hundreds of years, using the global standard known as paper. Today, government gives you a passport which you carry and present anywhere you wish, with broad acceptance. SSI simply makes the same thing possible digitally, and with significant advantages (zero-knowledge proofs/selective disclosure, revocation, mutual authentication, etc.).

This digital transformation of credentials simply hasn’t been possible until now, at least interoperably and on a global scale.

### Myth 3: SSI creates a national or “universal ID” credential.
There exists no intention (or delusion) that I am aware of that somehow SSI can, once it is broadly adopted, supplant a national ID system. On the contrary, as mentioned above, government should get excited about how SSI can complement and improve existing identity systems, whether national, regional, or otherwise.

SSI actually does not replace the trust of government or any other organization; it is simply a means for connecting and exchanging instantly authenticatable data. SSI is set of protocols, not an actor, and it has no inherent basis for trust other than the cryptographic properties that ensure the privacy and integrity of the data exchanged and the connection used to exchange it. What parties exchange over that connection, and whether to trust what was exchanged, is up to them.

Some governments already understand SSI and are leading out on its implementation. My prediction: all governments will eventually use SSI to issue credentials digitally, to better communicate with and interact with constituents, to streamline internal processes where slow verification bogs things down, to more strongly authenticate the people, organizations, and things they deal with, and to reduce the printing of paper and plastic.

#### SSI in the Developing World
Now that’s all fine and dandy for the developed world… but what about the billion-plus “invisibles” living without credentials, often in situations where a government is somehow struggling to issue them… can SSI help?

Quite possibly.

In some parts of the world, trust within a community is established by obtaining from a trusted individual a signed attestation that you’re worthy of obtaining a loan, for example. With SSI this could be done digitally rather than on paper, it could involve biometrics that strongly attach the attestation to the attestee and attestor, and it could include attestations and other potential credit scoring data from multiple sources.

I can imagine a baby born in a remote village and receiving her first “credentials” from her family and friends, who each give her attestations about her birth and their recollections of it. Pictures, videos, songs, and other precious memories could be added to her brand new digital wallet — which is now so much more than a wallet — and with guardianship of it tied to her parents. Who knows how such a set of credentials issued by loved ones might later be used, but my sense is that it could be vitally important some day.

I love the fact that SSI is powerful for both developed and developing worlds. I can’t wait to explore this topic more in the future.

### Myth 4: SSI gives absolute control over identity.
SSI gives its owner sovereign control over some aspects of identity, but not all. The digital wallet, DIDs, interaction history, consent receipts, private keys, and self-attested credentials are all self-sovereign, and can only be taken away with consent of the owner.

However… connections, relationships, and third-party issued credentials are not entirely self-sovereign, nor should they be. They represent (at least) two-sided relationships, and the other party to the relationship has some degree of control, too.

For example, if Abbott and Costello form a peer-to-peer SSI relationship and then subsequently break up, either Abbott or Costello can terminate the digital relationship — it’s not completely sovereign for either of them. As long as they both opt to keep it, the digital connection remains.

For third-party credentials, it is more nuanced. I recognize that some implementations of SSI do not allow for revocation, and that some people believe that credentials, once issued, should not be revocable, they should simply expire and be re-issued. We feel strongly that revocation is an essential component of credentialing in general — even if only to undo a mistaken issuance — and have implemented our thinking into Sovrin.

In the real world, I carry around my driver’s license and insurance card. If I drive drunk or neglect my premiums, these credentials can be revoked, but I still possess the plastic cards and can still use them to prove my age or address. Issuers don’t usually track someone down to confiscate the physical artifact after revoking it. (I recognize that this may not be true in some countries.)

Sovrin-style SSI makes this same balance possible with digital credentials, and usable in both meatspace and cyberspace: digital credentials such as licenses, permits, and the like can be held by the SSI owner in a self-sovereign digital wallet, and can still be revoked by their issuers, without the credentials themselves being removed from the wallet, and without verifiers needing to “phone home” (see below).

Importantly, revocation is optional, as it’s up to each issuer to build in the revocation ability during the issuance process. Without revocation, if the wrong Timothy Ruff undeservedly receives a Harvard diploma as a result of a clerical error, there would be no recourse other than asking the unintended recipient to destroy it or waiting for it to expire. (Good thing I’m honest.)

#### An Identity Game-Changer: Solving the “Phone Home” Problem
One very important (and exciting!) capability of Sovrin-style SSI credential revocation that’s not possible in the physical world: the ability of a verifier to instantly determine whether a presented credential has been revoked without contacting the issuer.

In the real world, physical credentials (e.g. a driver’s license) can be instantly checked for revocation against the issuer’s database. This introduces a problem, however, called the “phone home” problem: for every verifier of drivers licenses to have access to the official database from every state and every country, it would require a large, messy, many-to-many architecture, which introduces undesirable security, privacy, interoperability, and other complications, which is why it doesn’t happen often.

With Sovrin-style revocation, issuers can update anonymous revocation registries stored on the public ledger as often as every few minutes, where the updates become instantly available to verifiers anywhere¹. Doing this in a privacy-preserving manner is an important technological breakthrough that we have open-sourced and made freely available in the Hyperledger Indy codebase, implemented and running on the Sovrin network.

Revocation is an important topic that will be treated more fully in upcoming papers.

### Myth 5: There’s a “main” verifier of credentials.
I am often asked how identity is verified with SSI. The presumption seems to be that SSI has some designated actor or intermediary who does the authenticating, which conflates the IDP model of identity with SSI.


#### Today’s identity provider (IDP) model.
With true SSI there is no designated actor in the middle who verifies identities. Identity proofing services can provide a valuable service, but when government and financial institutions begin issuing verifiable credentials directly to identity owners, things get rather… simple.

With SSI, my bank or credit union, for example, first ensures that they’re dealing with me, then connects with me and issues one or more verifiable credentials that I can keep in my SSI digital wallet. Later, when I call in, walk in, or login, I present these credentials back to the institution, which they instantly verify and we’re done. No username or password, with all the attendant usability and security problems, is needed. See this excellent blog and video from IBM, Workday, ATB Financial and the province of British Columbia for how it all comes together.

And no intermediary is required. And no answering of silly questions about my birthday or mother’s maiden name, which are probably already in the public domain anyway thanks to Equifax.

If I later want to use that financial credential somewhere other than my financial institution — such as a website that would LOVE to onboard genuine humans who are provably banked — it can be strongly and instantly verified by any relying party I share it with, without having to check with the issuing financial institution.

#### ID Proofing & A Market for Credentials
Until government issuers begin issuing their credentials digitally, there is an opportunity for existing identity proofers to provide a valuable service for SSI owners.

Today, identity proofing work — typically verifying a person’s identity by verifying their government-issued credentials — is performed solely for the benefit of the organization that hired the proofer. For example, when Airbnb does identity verification of a new user, Airbnb is the only entity that benefits from the proofing work performed.

With SSI, that proofing work can result in a digital credential issued by the proofing service directly to the person being proofed, where he/she can use it with Airbnb or anywhere else, for as long as that proof is considered current. Future verifiers who accept this credential will benefit even though they didn’t originally pay for the proofing work, but they could remunerate the original proofing service each time the credential is verified, creating an interesting recurring business model for quality identity proofers.

This is just one example of what a market for verifiable credentials might look like.

### Myth 6: There’s a built-in method of authenticating.
Real SSI doesn’t dictate a specific means of authentication, either. It offers a protocol that supports any authentication method that two (or more) parties opt to use. One implementation might use facial or voice biometrics while another uses proof of location, and another simply exchanges digitally signed attestations, which are incredibly strong.

When it comes to usernames and passwords… I wish shared secrets would go away forever, and thankfully SSI absolutely does have the potential to eliminate usernames and passwords, as we saw in IBM’s video above.

Innovation in biometrics — a big part of everyone’s digital future — is moving at a breakneck speed. With SSI there’s no need to lock into one biometric modality, or even to the entire category of biometrics; it’s possible to abstract the means of authentication as a pluggable type of verifiable credential, leaving flexibility for future technologies.

I’m particularly interested in authentication modalities involving location or state such as velocity, temperature, or other calculations, which will have broad implications for the Internet of Things. The possibilities are exciting, and the required puzzle pieces now exist to make this a reality.

### Myth 7: User-centric identity is the same as SSI.
I addressed one aspect of this myth in my last post: some identity services call their offerings self-sovereign, when they’re really still siloed and dependent on a single organization. Turn off the servers on that organization, and it all goes away.

I first saw the term “user-centric identity” in Christopher Allen’s seminal post, The Path to Self-Sovereign Identity, which describes it in greater detail than I will here. Basically, user-centric identity gives the user greater control than before, and that’s a good thing, but it never realized its original intent — user independence — and it actually left large intermediaries with even more power than before. Facebook and Google, the biggest beneficiaries of the move to user-centric identity, would call their services user-centric.

Even the term gives it away: you’re still a user and not the owner, and that means the underlying service is siloed or federated, not self-sovereign. Of course with SSI there are services provided by third parties, such as cloud agent hosting and relationship management apps and tools, but they are modular and replaceable.

In simple terms, with SSI you can fire your service providers without losing your data or relationships, which you can’t easily do when you are a user. Before long we’ll see Facebook without Facebook and Twitter without Twitter, as SSI makes possible completely decentralized alternatives to those services: you can fire them and switch providers without losing your friends, followers, etc.

Why is the independence that SSI affords so important? Two primary reasons:

1. Permanent, vendor-independent control of data, including credentials, consent, history, and more;
2. Permanent, vendor-independent control of relationships, including discrete, encrypted, peer-to-peer connections with each.

Imagine changing your address in only one master place (finally!), and only those you allow to subscribe to it automatically getting the update. Imagine having one master set of contacts (finally!), each with a persistent, encrypted communication link that only you and that party have the keys to, and no vendor in the world can take them away.

I get excited every time I think about it.

User-centric identity may seem on the surface to be similar to SSI, but under the hood, where it counts most, it suffers from all the disadvantages of siloed or federated/IDP-based identity.

---

In sum, there are many myths about SSI that need to be cleared up, not just seven. There are also many new capabilities that SSI brings that I have barely touched on so far. It is a watershed event in digital identity — such a different way of thinking that we will need to experiment with the messaging until we can achieve accuracy with brevity when describing it.

