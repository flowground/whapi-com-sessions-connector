# ![LOGO](logo.png) Sessions **flow**ground Connector

## Description

A generated **flow**ground connector for the Sessions API (version 2.0.0).

Generated from: https://api.apis.guru/v2/specs/whapi.com/sessions/2.0.0/swagger.json<br/>
Generated at: 2019-05-07T17:44:54+03:00

## API Description

The William Hill Sessions API uses a central authentication service (CAS*) on all resources that require access to a customer’s account or betting functionality. To authenticate, you’ll need to supply a sportsbook username and password, in return you will be given an authentication ticket, which you can use on the majority of requests found within our services. <br /><br /><br /> The Sessions API should be used whenever you want to login a customer and:<br /><br /> <ul> <li>continue to use the William Hill API for that customer’s transactions</li> <li>use other CAS-enabled William Hill services outside the suite of APIs</li> </ul> <br /> CAS is an enterprise Single Sign-On solution for web services (see https://wiki.jasig.org/display/CAS/Home). It is used by many William Hill services. <br /> Note: all requests must be executed over HTTPS and include an API key and secret.<br /><br /><br /> <b>Authentication Ticket Expiration Times</b><br /><br /> When a customer is logged in using the Sessions API, they are given an Authentication Ticket; using this ticket on subsequent API requests gives you access to account activities (such as placing a bet, deposits, etc). However, this ticket is only valid for a given period of time depending on how it is used. If the ticket is used and then has a period of inactivity longer than 7,200 seconds (2 hours), then the ticket will expire and further requests using the ticket will be denied - in effect, a customer has been logged out and will need to authenticate again. <br /><br /><br /> Normally, any ticket issued only has a maximum life expectancy of 28,000 seconds (8 hours) after which it can no longer be used, even if it has been used regularly. The customer again will be effectively logged out and will need to authenticate again. If you wish to avoid this, you need to set the query parameter extended to Y, which will enable your application to generate a ticket valid for 60 days without expiring due to inactivity. <br />

## Authorization

Supported authorization schemes:
- API Key
## Actions

### Logs in a customer and obtains an authentication ticket.

> Logs in a customer by obtaining an authentication ticket. It can then be used directly with the other William Hill APIs to access a customer's sportsbook account, place a bet, etc.

*Tags:* `Sessions`

#### Input Parameters
* `apiSecret` - _required_ - Another unique identifier for your application.
* `fields` - _optional_ - Specify an absolute field list to return (Comma Separated List)
* `include` - _optional_ - Specify fields in addition to the default to return (Comma Separated List)
* `exclude` - _optional_ - Specify fields from the default to exclude (Comma Separated List)

### Log out a customer.

> Logs out a customer.

*Tags:* `Sessions`

#### Input Parameters
* `apiSecret` - _required_ - Another unique identifier for your application.
* `tgt` - _required_ - Ticket Granting Ticket obtained from a previous request

### Checks the validity of a session ticket.

*Tags:* `Sessions`

#### Input Parameters
* `apiSecret` - _required_ - Another unique identifier for your application.
* `tgt` - _required_ - Ticket Granting Ticket obtained from a previous request

### Obtains a one-time Service Ticket that can be used to access other William Hill services.

> Obtains a one-time Service Ticket that can be used to access other CAS enabled William Hill services that are not available through the standard suite of APIs. You first need to have logged in a customer to obtain an Authentication Ticket.

*Tags:* `Sessions`

#### Input Parameters
* `apiSecret` - _required_ - Another unique identifier for your application.
* `tgt` - _required_ - Ticket Granting Ticket obtained from a previous request
* `target` - _required_ - The target URL of the CAS enabled service that you want to use with the service ticket.
* `fields` - _optional_ - Specify an absolute field list to return (Comma Separated List)
* `include` - _optional_ - Specify fields in addition to the default to return (Comma Separated List)
* `exclude` - _optional_ - Specify fields from the default to exclude (Comma Separated List)

## License

**flow**ground :- Telekom iPaaS / whapi-com-sessions-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
