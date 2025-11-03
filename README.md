                Internet
                   |
               +---IGW---+
               |         |
     +---------+--+   +--+---------+
     | Public Subnet A | | Public Subnet B |
     +------------------+ +----------------+
            |  (AZ0)                (AZ1)
            |
        EC2 Pública
        - HTTP 80 abierto
        - SSH opcional (AdminCidr)
        - SSM habilitado

     +------------------+ +----------------+
     | Private Subnet A | | Private Subnet B |
     +------------------+ +----------------+
            |
        EC2 Privada
        - SSH solo desde SG Pública
        - Sin NAT (salida a Internet OFF por defecto)

S3 bucket (versionado, cifrado, lifecycle 30d, TLS-only)
IAM opcional (usuario programático S3 RW)
CloudWatch (CPU>80%) -> SNS Email
