---
description: Passpoint®
---

# Configuration Introduction

TIP Open WiFi devices implement support for both the air interface and systems interfaces necessary to support Passpoint® Release 2 and above. Once also termed Hotspot 2.0, IEEE 802.11u specified added air interface fields exposing Access Network Query Protocol interactions for clients to discovery Access Point capabilities. 

Wi-Fi Alliance expanded ANQP to include Online Signup \(OSU\) concepts to leverage seamless onboarding and client security for Passpoint® networks. Following on from these efforts, Wireless Broadband Alliance has provided the necessary system interfaces for identity, security, mobile offload within a common federated operator solution known as OpenRoaming. 

TIP Open WiFi enables operators to deploy the full range of Passpoint® and OpenRoaming solutions. 

<table>
  <thead>
    <tr>
      <th style="text-align:left">Term</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Operator</td>
      <td style="text-align:left">
        <p>Wi-Fi Infrastructure Operator</p>
        <p>Access Network Provider (ANP) as defined by OpenRoaming</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Venue</td>
      <td style="text-align:left">Deployed location of Wi-Fi service</td>
    </tr>
    <tr>
      <td style="text-align:left">Identity Provider</td>
      <td style="text-align:left">
        <p>Subscriber authenticating service provider</p>
        <p>Home Service Provider (HSP) as defined by OpenRoaming</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Roaming Exchange</td>
      <td style="text-align:left">Operator and Identity Provider Authentication, Authorization, Accounting</td>
    </tr>
    <tr>
      <td style="text-align:left">ANQP</td>
      <td style="text-align:left">
        <p>Access Network Query Protocol contains:</p>
        <ul>
          <li>Domain</li>
          <li>Venue Name</li>
          <li>Venue Info</li>
          <li>Operator Friendly Name</li>
          <li>IP Type</li>
          <li>WAN Metric</li>
          <li>Connection Capability</li>
          <li>Operating Class</li>
          <li>Authentication Type</li>
          <li>Service Providers List</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">GAS</td>
      <td style="text-align:left">
        <p>Generic Advertisement Layer 2 Service for client query</p>
        <ul>
          <li>Client query returns:
            <ul>
              <li>Organization Identifier / Service Provider Identity</li>
              <li>Domain</li>
              <li>Authentication</li>
              <li>Roaming Consortium List</li>
              <li>Network Access Identifier Realm (NAI)</li>
              <li>3GPP Network Data</li>
            </ul>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">OSU</td>
      <td style="text-align:left">
        <p>Online Signup - Advertised over ANQP contains:</p>
        <p></p>
        <ul>
          <li>OSU SSID</li>
          <li>OSU URI</li>
          <li>OSU Method</li>
          <li>OSU Available Icons</li>
          <li>OSU ESS (OSEN) SSID</li>
          <li>OSU Description</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">OSEN</td>
      <td style="text-align:left">OSU Server Authenticated Layer 2 Encryption Network</td>
    </tr>
  </tbody>
</table>

 

