# Oblivious HTTP Working Group (OHTTP) Charter

In a number of different settings, interactions between clients and servers
involve information that could be sensitive when associated with client
identity.  Client-server applications built on HTTP reveal aspects of client
identity to servers through these interactions, especially source addresses.
Even without client identity, a server might be able to build a profile of
client activity by correlating requests from the same client over time.

In HTTP-based applications where the information included in requests does not
need to be correlated, the Oblivious HTTP protocol allows a supporting server to
accept requests via a proxy.  The proxy ensures that the server cannot see
source addressing information for clients, which prevents servers linking
requests to the same client using such information.  Encryption ensures that the
proxy is unable to read requests or responses.  However, if the proxy and server
collude, then neither of these privacy properties hold.

Applications and use cases best suited for the Oblivious HTTP protocol are those
that have discrete, transactional queries that might reveal small amounts of information over
time.  Examples include DNS queries, data or telemetry submission, and
certificate revocation checking. In some of these application deployments, the
relationship between client, server, and cooperating proxy is typically
configured out-of-band.

General purpose HTTP applications such as web browsing are not in scope for the
Oblivious HTTP protocol. Broad applicability is limited by multiple factors,
including the need for explicit server support of the protocol. In contrast,
transport-level proxies such as HTTP CONNECT or MASQUE are a more appropriate
mechanism for those use cases, as they allow connecting to unmodified servers.

The OHTTP working group will define the Oblivious HTTP protocol, a method of
encapsulating HTTP requests and responses that provides protected, low-latency
exchanges.  The working group will define any encryption scheme necessary and
supporting data formats for carrying encapsulated requests and responses, plus
any key configuration that might be needed to use the protocol.

The OHTTP working group will include an applicability statement that documents
the limitations of this design and any usage constraints that are necessary to
ensure that the protocol is secure.  The working group will consider the
operational impact as part of the protocol design and document operational
considerations.

The working group will prioritize work on the core protocol elements as
identified.  In addition, the working group may work on other use cases and
deployment models, including those that involve discovery of OHTTP proxies or
servers and their key configurations.

The OHTTP working group will work closely with other groups that develop the
tools that Oblivious HTTP depends on (HTTPbis for HTTP, CFRG for HPKE) or that
might use Oblivious HTTP (DPRIVE for DNS over HTTPS).

The working group will use draft-thomson-http-oblivious as input.
