
A host or service's certificate or public key can be added to an
application at development time, or it can be added upon first encountering
the certificate or public key. The former - adding at development time -
is preferred since preloading the certificate or public key out of band
usually means the attacker cannot taint the pin.
