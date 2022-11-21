# Challenge #2
# We need to write code that will query the meta data of an instance within GCP and provide a json formatted output. The choice of language and implementation is up to you. 

# Link Referred : https://cloud.google.com/compute/docs/reference/rest/v1/backendServices/get

# To do challenge 2, I have created a virutal machine on GCP using the rest api querying VMs metadata in jason format 

# To test or verify metadata of VM, Call this method on live data and see the result. Experiment with authorization and field settings. For help, check the APIs Explorer documentation.

# Request parameters 1). project 2). backendService

# If successful, the response body contains data with the following structure:

# Backend services in Google Compute Engine can be either regionally or globally scoped.

Global
Regional
For more information, see Backend Services.

JSON representation

{
  "kind": string,
  "id": string,
  "creationTimestamp": string,
  "name": string,
  "description": string,
  "selfLink": string,
  "backends": [
    {
      "description": string,
      "group": string,
      "balancingMode": enum,
      "maxUtilization": number,
      "maxRate": integer,
      "maxRatePerInstance": number,
      "maxRatePerEndpoint": number,
      "maxConnections": integer,
      "maxConnectionsPerInstance": integer,
      "maxConnectionsPerEndpoint": integer,
      "capacityScaler": number,
      "failover": boolean
    }
  ],
  "healthChecks": [
    string
  ],
  "timeoutSec": integer,
  "port": integer,
  "protocol": enum,
  "fingerprint": string,
  "portName": string,
  "enableCDN": boolean,
  "sessionAffinity": enum,
  "affinityCookieTtlSec": integer,
  "region": string,
  "failoverPolicy": {
    "disableConnectionDrainOnFailover": boolean,
    "dropTrafficIfUnhealthy": boolean,
    "failoverRatio": number
  },
  "loadBalancingScheme": enum,
  "connectionDraining": {
    "drainingTimeoutSec": integer
  },
  "iap": {
    "enabled": boolean,
    "oauth2ClientId": string,
    "oauth2ClientSecret": string,
    "oauth2ClientSecretSha256": string
  },
  "cdnPolicy": {
    "cacheKeyPolicy": {
      "includeProtocol": boolean,
      "includeHost": boolean,
      "includeQueryString": boolean,
      "queryStringWhitelist": [
        string
      ],
      "queryStringBlacklist": [
        string
      ],
      "includeHttpHeaders": [
        string
      ],
      "includeNamedCookies": [
        string
      ]
    },
    "signedUrlKeyNames": [
      string
    ],
    "signedUrlCacheMaxAgeSec": string,
    "requestCoalescing": boolean,
    "cacheMode": enum,
    "defaultTtl": integer,
    "maxTtl": integer,
    "clientTtl": integer,
    "negativeCaching": boolean,
    "negativeCachingPolicy": [
      {
        "code": integer,
        "ttl": integer
      }
    ],
    "bypassCacheOnRequestHeaders": [
      {
        "headerName": string
      }
    ],
    "serveWhileStale": integer
  },
  "customRequestHeaders": [
    string
  ],
  "customResponseHeaders": [
    string
  ],
  "securityPolicy": string,
  "edgeSecurityPolicy": string,
  "logConfig": {
    "enable": boolean,
    "sampleRate": number
  },
  "securitySettings": {
    "clientTlsPolicy": string,
    "subjectAltNames": [
      string
    ]
  },
  "localityLbPolicy": enum,
  "consistentHash": {
    "httpCookie": {
      "name": string,
      "path": string,
      "ttl": {
        "seconds": string,
        "nanos": integer
      }
    },
    "httpHeaderName": string,
    "minimumRingSize": string
  },
  "circuitBreakers": {
    "maxRequestsPerConnection": integer,
    "maxConnections": integer,
    "maxPendingRequests": integer,
    "maxRequests": integer,
    "maxRetries": integer
  },
  "outlierDetection": {
    "consecutiveErrors": integer,
    "interval": {
      "seconds": string,
      "nanos": integer
    },
    "baseEjectionTime": {
      "seconds": string,
      "nanos": integer
    },
    "maxEjectionPercent": integer,
    "enforcingConsecutiveErrors": integer,
    "enforcingSuccessRate": integer,
    "successRateMinimumHosts": integer,
    "successRateRequestVolume": integer,
    "successRateStdevFactor": integer,
    "consecutiveGatewayFailure": integer,
    "enforcingConsecutiveGatewayFailure": integer
  },
  "network": string,
  "subsetting": {
    "policy": enum
  },
  "connectionTrackingPolicy": {
    "trackingMode": enum,
    "connectionPersistenceOnUnhealthyBackends": enum,
    "idleTimeoutSec": integer,
    "enableStrongAffinity": boolean
  },
  "maxStreamDuration": {
    "seconds": string,
    "nanos": integer
  },
  "compressionMode": enum,
  "serviceBindings": [
    string
  ],
  "localityLbPolicies": [
    {
      "policy": {
        "name": enum
      },
      "customPolicy": {
        "name": string,
        "data": string
      }
    }
  ]
}