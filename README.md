<div align="center">
  <h1>KProxy</h1>
  <p><strong>Connectivity. Refined.</strong></p>
  <p>Advanced proxy connectivity for Android.<br>Intelligent routing, precise diagnostics and your own infrastructure.</p>
  <p><code>v0.16.14</code> &nbsp; / &nbsp; <code>Build 30</code> &nbsp; / &nbsp; <code>Android</code></p>
  <p><strong>€5 once</strong> &nbsp; · &nbsp; No recurring app subscription &nbsp; · &nbsp; 29 languages</p>
</div>

<p align="center">
  <a href="https://www.patreon.com/c/KytheApps"><img width="347" height="97" alt="изображение" src="https://github.com/user-attachments/assets/799b5245-1e03-42a3-9ebd-6222fd76e1f2" /></a>
</p>
<p align="center"><sub>Connectivity, on your terms.</sub></p>
<p align="center">
<img width="1262" height="996" alt="изображение" src="https://github.com/user-attachments/assets/b373bba6-28ce-4e27-8bda-d3f0283fac1a" />
</p>

---

## A more thoughtful way to connect

Hi, I'm Kythe, an independent developer. KProxy started with a fairly simple idea. I wanted a better way to use my own proxy servers on Android, with more control over the connection and a clearer understanding of what happens when something goes wrong.

Over time, that idea became a much deeper engineering project. I built a configurable networking client around the Android VPN interface, integrated advanced native transports and spent a great deal of time working on the details that make connections more reliable.

I wanted KProxy to feel simple on the surface without taking away the flexibility that experienced users appreciate. The monochrome interface black and white, sometimes gray, the small interactions and the diagnostic tools all come from that same idea.

> **Your infrastructure. Your decisions.**
>
> A networking tool should give you more control over your connection, not make decisions about it behind your back.

<p align="center"><sub><a href="#the-experience">Experience</a> &nbsp; · &nbsp; <a href="#the-transport-stack">Transports</a> &nbsp; · &nbsp; <a href="#intelligent-routing">Routing</a> &nbsp; · &nbsp; <a href="#engineering-and-testing">Engineering</a> &nbsp; · &nbsp; <a href="#get-kproxy">Get KProxy</a></sub></p>

---

## The experience

KProxy brings everyday proxy connections, advanced network configuration and useful engineering tools into one interface. Start with a familiar HTTP or SOCKS profile, or build a more sophisticated route when you need it.

| Capability | What it brings to KProxy |
| --- | --- |
| **Turbo VPN** | Advanced tunnel compatibility and controlled connection recovery in a unified experience. |
| **Smart Escalation Engine** | Bounded recovery attempts based on connection failures, route priorities and cooldowns. |
| **Proxy chains** | Flexible multi-hop routing with up to 12 configured nodes. |
| **Rescue Bridges** | Configurable entry routes that can help reach your original proxy without changing the final TCP exit. |
| **Network Lab** | Practical DNS, TLS, latency and transfer diagnostics through the full tunnel. |
| **Hybrid UDP** | An optional separate UDP route while retaining your selected TCP proxy. |
| **Application routing** | Choose which applications enter the tunnel and whether local network traffic is excluded. |
| **Configuration management** | Saved profiles, batch import, QR codes and technical server lists. |


<p align="center">
<img height="490" alt="08" width="240" alt="KProxy dashboard" src="https://github.com/user-attachments/assets/44408ee3-f16f-453f-bedb-8f53e22274b0" />&nbsp;
<img height="490" alt="02" width="240" alt="KProxy dashboard" src="https://github.com/user-attachments/assets/b4c933fb-cc41-4221-8a83-19339e61120c" />&nbsp;
<img height="490" alt="06" width="240" alt="KProxy dashboard" src="https://github.com/user-attachments/assets/2e3f4255-bf0a-47ce-95e2-714ec558d76c" />&nbsp;
<img height="490" alt="01" width="240" alt="KProxy dashboard" src="https://github.com/user-attachments/assets/92c41f56-0a6b-4bef-b75e-c90cd378f64b" />
</p>
<p align="center"><sub>A focused interface with advanced controls close at hand.</sub></p>


> Simple when you need it. Deep when you want it.

---

## The transport stack

Different networks and servers call for different technologies. KProxy supports traditional proxy protocols alongside a range of modern transports, allowing you to work with the infrastructure you already have.

### Classic connectivity

| Protocol | Where it fits |
| --- | --- |
| `HTTP` | Conventional HTTP CONNECT proxying for TCP connections. |
| `HTTPS` | HTTP proxy connections with TLS protection between the client and proxy. |
| `SOCKS4` | Traditional IPv4 TCP proxying. |
| `SOCKS4a` | TCP proxying with destination hostname resolution at the proxy. |
| `SOCKS5` | Flexible TCP connectivity and optional UDP relay on compatible servers. |
| `SOCKS5h` | SOCKS5 with destination hostname resolution handled by the proxy. |

### Advanced connectivity

| Technology | What makes it useful |
| --- | --- |
| `VLESS` | Flexible proxy connections with compatible transport and security configurations. |
| `REALITY` | An alternative security layer for compatible VLESS or Trojan configurations. |
| `XTLS Vision` | A specialized flow option for compatible VLESS connections. |
| `WebSocket` | Web-compatible transport for suitable server configurations. |
| `gRPC` | A transport option built around HTTP/2 and RPC framing. |
| `XHTTP` | Flexible HTTP-based transport with supported stream and connection settings. |
| `Trojan` | Proxy connectivity using compatible TLS or REALITY configurations. |
| `Shadowsocks-2022` | An encrypted proxy protocol with TCP and UDP capabilities. |
| `Hysteria 2` | A QUIC-based proxy protocol designed for challenging network conditions. |
| `Salamander` | An optional obfuscation mechanism for compatible Hysteria 2 servers. |
| `TUIC v5` | QUIC-based proxy connectivity through KProxy's own client integration. |

These are not all interchangeable protocols. Some are transport layers, security mechanisms or flow options. KProxy brings them together while respecting their individual configuration requirements. External interoperability depends on the selected server, network and supported combination.

---

## Intelligent routing

### Turbo VPN

Turbo VPN brings the advanced networking capabilities of KProxy into a more convenient experience. It combines tunnel compatibility and connection recovery while keeping your configured profile at the center of the connection.

Underneath the interface, KProxy handles IPv4 and IPv6 routing, DNS processing, TCP streams and supported UDP paths. You can keep using a conventional proxy without having to configure every low-level option manually.

### Smart Escalation Engine

A network failure should not automatically mean the end of a connection. KProxy can classify eligible transport errors and evaluate permitted alternative routes with a bounded connection deadline, route priorities and cooldowns.

The engine takes care not to repeat application data that has already been sent. Authentication failures, certificate errors and socket protection failures stop unsafe recovery attempts rather than weakening security to force a connection.

| Mode | Behavior |
| --- | --- |
| **Off** | Uses the configured route without automatic escalation. |
| **Automatic** | Evaluates permitted transport adjustments and configured bridges when appropriate. |
| **DPI Only** | Uses compatible local transport adjustments without switching to a bridge. |
| **Strict Bridge** | Requires an authorized bridge and does not silently fall back to a direct route. |

### Multi-hop chains and Rescue Bridges

Build routes of up to 12 configured nodes, subject to transport compatibility. A compatible entry bridge can provide a path to the existing proxy chain while retaining the intended final TCP exit.

```text
Android device > KProxy > Entry bridge > Your proxy > Internet
```

Bridge priorities, parallel health checks and route information help you choose between the paths you have configured. KProxy does not supply a managed relay network, and a completely unreachable proxy requires a reachable alternative path.

---

## Network compatibility

KProxy uses Android's `VpnService` to provide a device-level tunnel for the applications you select. The networking stack is designed to handle more than a conventional system proxy setting.

| Technology | Purpose |
| --- | --- |
| **IPv4 and IPv6 TUN** | Handles both IP address families within the VPN interface. |
| **FakeIP** | Maps supported domain-based connections through virtual IP addresses. |
| **SNI destination override** | Provides hostname-aware destination handling where the TLS information is available. |
| **Dynamic AAAA guard** | Adapts IPv6 DNS answers to applicable connection capabilities. |
| **Protected DoH bootstrap** | Resolves domain-based entry nodes through protected DNS over HTTPS. |
| **Happy Eyeballs** | Races eligible TCP addresses across available IP families and closes unused sockets. |
| **QUIC Fast-Reject** | Returns a prompt rejection when UDP is unavailable, allowing applications to choose TCP where supported. |
| **Network-aware sockets** | Keeps physical socket binding and route lifetime associated with the active network. |

### TCP and UDP

Native UDP support includes active reachability checks, bounded association handling and support for multiple destinations on compatible relays. This allows KProxy to distinguish a successful proxy handshake from an actually working UDP path.

Hybrid UDP can use a separately configured UDP node while leaving the TCP exit unchanged. Its UDP exit address may differ, and removing the selected UDP node blocks that route instead of silently selecting another one.

Full-Cone behavior was confirmed in a controlled native SS2022 relay test on the physical device. This is evidence of the tested relay behavior, not a promise that every server or mobile operator supports the same NAT mapping.

---

## Network Lab

One of my favorite parts of KProxy is the ability to look at a connection in more detail instead of simply getting a green or red status indicator.

Network Lab gives you a closer look at the network using actual diagnostic requests. It helps separate connection establishment, TLS negotiation and data transfer from one another.

- Full tunnel readiness and connection diagnostics.
- DNS response times, TCP connection and TLS setup measurements.
- Time to first byte and controlled CDN transfers of 128 KiB and 1 MiB.
- Route information, transport status and connection evidence.
- Bridge health and media checks.
- Separate interpretation of HTTP 403 and 429 responses alongside control results.

> **Understand the connection instead of guessing.**
>
> A timeout is an observation, not proof of a particular filtering mechanism. KProxy's diagnostics are designed around that distinction.

---

## Privacy and control

Privacy starts with knowing which infrastructure you are using and being able to decide how traffic reaches it.

KProxy is a client for your own compatible proxies and bridges. It does not require you to use an included VPN provider or replace your selected TCP exit with an unknown service.

| Protection | Design approach |
| --- | --- |
| **Encrypted configuration** | Android Keystore and AES-GCM protect stored profiles and credentials. |
| **Certificate verification** | Secure transport connections validate the remote certificate where applicable. |
| **Protected sockets** | Physical transport sockets are protected and bound before connecting. |
| **Controlled recovery** | Security and authentication failures do not trigger unsafe retries. |
| **Fail-closed behavior** | The tunnel can remain in place during adapter failure and policy replacement. |
| **Per-app rules** | Include or exclude applications according to your routing preferences. |
| **LAN bypass** | Optional local network access while retaining virtual DNS and FakeIP routing inside the tunnel. |

KProxy does not make an unencrypted HTTP or SOCKS connection encrypted by itself. The privacy of a connection also depends on the selected transport, server and destination. Android Always-on VPN with Block connections without VPN is needed for protection when the VPN service stops unexpectedly. Explicitly excluded traffic follows its own routing rules.

---

## Make it yours

KProxy is built for people who manage their own connections. Instead of entering every server again, you can organize your profiles and use the import methods that fit your existing setup.

| Configuration | Supported options |
| --- | --- |
| **Profiles** | Save, edit and organize individual proxy and bridge configurations. |
| **Import** | 12 URI schemes, plain text, Base64, JSON, SIP008 and bulk clipboard import. |
| **QR codes** | Import from the camera or a saved image. |
| **Server lists** | Technical HTTPS lists with protected retrieval, encrypted URLs and tokens. |
| **Refresh** | Optional scheduled updates, duplicate detection and preservation of manual edits where supported. |
| **Expert settings** | Detailed routing, transport, DNS and application policy controls. |

Technical server subscriptions are configuration sources, not payment subscriptions. They do not unlock a paid feature tier inside KProxy.

---

## Engineering and testing

I spend a lot of time testing the parts of KProxy that users may never see directly. Socket lifecycle management, DNS queues, native resource cleanup, certificate verification and failure recovery are just as important to me as the interface itself.

The 0.16.14 release was built, signed, installed and tested on a physical Xiaomi 15 running Android 17. The installation preserved the existing encrypted configuration and original signing identity.

<table>
  <tr>
    <td align="center" width="25%"><h2>345</h2><sub>JUnit scenarios</sub></td>
    <td align="center" width="25%"><h2>732</h2><sub>Accounted test runs</sub></td>
    <td align="center" width="25%"><h2>29</h2><sub>Language catalogs</sub></td>
    <td align="center" width="25%"><h2>16 KiB</h2><sub>Native alignment</sub></td>
  </tr>
</table>

### Release verification

| Check | Recorded result |
| --- | --- |
| Debug unit tests | **345 / 345 passed** |
| Release unit tests | **345 / 345 passed** |
| Native Go tests | **29 top-level tests passed** |
| Python validation tests | **13 passed** |
| Android Lint | **0 errors** in Debug and Release |
| Release build and R8 | Passed |
| JNI and native route pool | Passed on arm64 |
| APK signing and AAB validation | Passed |
| Native ELF and APK alignment | 16 KiB verified |
| Installed APK integrity | SHA-256 matched the release file |
| Configuration preservation | Verified across installation and device tests |
| Separate application UID test | Fail-closed TCP behavior verified during adapter failure |
| Native UDP and proxy cascade | Verified in the tested device configuration |
| Runtime dependency audit | 45 Go modules and 60 Android artifacts reviewed, no unresolved licenses reported |

The 732 figure counts 345 JUnit scenarios run in both build variants, plus 29 top-level Go tests and 13 Python tests. It does not count nested assertions as separate tests or include the physical device checks.

### Measured, not imagined

Selected full tunnel control measurements from the 0.16.14 release on Xiaomi 15 using the tested HTTP proxy.

| Destination or operation | Observed result |
| --- | --- |
| Instagram TLS setup | 1,375 ms |
| Threads TLS setup | 293 ms |
| YouTube TLS setup | 441 ms |
| example.com TLS setup | 272 ms |
| 1 MiB CDN transfer | 12.112 Mbit/s |
| Local DNS control responses | 0 to 1 ms |
| Local QUIC rejection without UDP | 0 ms at the measured resolution |

A separate direct proxy control for Instagram completed the HTTP CONNECT stage but timed out during TLS. The same destination completed TLS through the KProxy full tunnel in the documented test. This demonstrates the observed difference without assigning an unsupported cause to it.

### Stability under load

<table>
  <tr>
    <td align="center" width="33%"><h2>160</h2><sub>Concurrent TLS connections</sub></td>
    <td align="center" width="33%"><h2>80 MiB</h2><sub>Across two test rounds</sub></td>
    <td align="center" width="33%"><h2>0</h2><sub>Idle file descriptor growth</sub></td>
  </tr>
</table>

Two TCP stress rounds completed without errors at a preceding checkpoint of the networking engine. The second round recorded median TLS setup of 556 ms and a 95th percentile of 776 ms. The file descriptor count returned to its baseline after the documented idle interval.

These stress results precede the last UDP and bootstrap changes. They are not a new stress benchmark of the final APK. All measurements describe specific test conditions rather than guaranteed Internet speeds.

### Everyday connectivity

In my own practical acceptance tests, I checked Instagram, Reels, Stories, Threads, Telegram, YouTube and Discord, along with background connectivity, Wi-Fi and mobile network transitions, and external IP, DNS and IPv6 behavior. All nine personal acceptance checks passed in my configuration.

Those results complement the automated release checks. They do not guarantee every application, server or network will behave the same way.

---

## Built in layers

The Android interface is only one part of KProxy. Its networking architecture combines Kotlin and Java with native C and Go components, connected through JNI.

| Layer | Responsibility |
| --- | --- |
| Android / Kotlin / Java | Interface, profiles, configuration and connection policies. |
| VpnService / TUN / Hev | Packet handling and local tunnel integration. |
| Go / JNI / Xray / TUIC | Native transport support and route lifecycle management. |
| User infrastructure | The compatible proxies and bridges you choose to connect through. |

The release integrates Xray-core, a modified Hev tunnel with a project-specific backpressure fix and a KProxy TUIC v5 client built on quic-go. Active native routes remain pinned while connections use them, and unused routes are eligible for controlled cleanup.

---

## Designed for a wider world

KProxy is available in 29 languages. The verified release contains 881 localization keys per catalog, 10 plural groups and 46 built-in help topics. Localization structure, placeholders and translated legal resources passed the project's validators.

<details>
<summary><strong>Supported languages</strong></summary>

Arabic, Bengali, Chinese, Czech, Dutch, English, Filipino, Finnish, French, German, Greek, Hebrew, Hindi, Indonesian, Italian, Japanese, Korean, Norwegian Bokmål, Persian, Polish, Portuguese, Romanian, Russian, Spanish, Swedish, Thai, Turkish, Ukrainian and Vietnamese.

The structural checks establish localization completeness, not professional proofreading of every translation.

</details>

---

## Product evolution

KProxy has grown through a series of engineering iterations. The following milestones reflect documented development builds and the current verified release, rather than an invented history of public releases.

<details open>
<summary><strong>0.16.14 / Build 30</strong> &nbsp; · &nbsp; November 26, 2026</summary>

- Integrated Turbo VPN, Smart Escalation and four transport modes.
- Added the Go and JNI transport engine with Xray-core and a custom TUIC v5 client.
- Expanded VLESS, REALITY, XHTTP, Trojan, Shadowsocks-2022 and Hysteria 2 support.
- Added active UDP probing, Hybrid UDP and native TCP address racing.
- Improved full tunnel DNS, FakeIP, IPv6 handling, native backpressure and route resource management.
- Expanded bridge management, batch imports and technical server list handling.
- Verified signed installation, configuration preservation and full tunnel controls on Xiaomi 15.
- Synchronized 29 localization catalogs and completed the documented release test suite.

</details>

<details>
<summary><strong>0.16.13 / Build 29</strong> &nbsp; · &nbsp; Route hardening</summary>

Added shared route deadlines, clearer transport failure classification and expanded diagnostic evidence. This was an engineering candidate preceding the verified 0.16.14 release.

</details>

<details>
<summary><strong>0.16.12 / Build 28</strong> &nbsp; · &nbsp; Network lifecycle</summary>

Improved TLS buffering, handshake metrics, physical network monitoring and network-aware DNS cache management.

</details>

<details>
<summary><strong>0.16.11 / Build 27</strong> &nbsp; · &nbsp; Compatibility</summary>

Added SOCKS4 and SOCKS4a connectivity, strict bridge routing and expanded diagnostic support for configured bridges.

</details>

<details>
<summary><strong>0.16.10 / Build 26</strong> &nbsp; · &nbsp; Diagnostics and concurrency</summary>

Separated connection worker pools, introduced bounded media transfer checks and extended the available network diagnostics.

</details>

---

## Get KProxy

<div align="center">
  <h3>Pay once. Make it yours.</h3>
  <h1>€5</h1>
  <p>One-time purchase. No recurring app subscription.</p>
  <p><sub>Applicable taxes or VAT may be added at checkout.</sub></p>
</div>

I wanted the commercial model to be straightforward. Buy the client once and continue using the purchased application without another recurring app subscription.

- Full client feature set without paid feature tiers.
- No in-app purchases or recurring app payments.
- Use your own compatible proxy infrastructure.
- Access the advanced controls and diagnostic tools included in the release.

KProxy is not a bundled VPN service. Proxy servers and other third-party services are obtained separately and may have their own costs. The official purchase listing determines final pricing, availability and delivery terms.

---

<details>
<summary><strong>Compatibility and important details</strong></summary>

The verified release includes native libraries for arm64-v8a, armeabi-v7a and x86_64. Physical device testing was conducted on arm64. External interoperability across all advanced transport combinations, comprehensive packet-level leak testing, prolonged Doze behavior and carrier-level Full-Cone NAT remain areas for further verification. Automated cellular handover was not confirmed in the release environment, although my subsequent personal network switching check passed.

KProxy cannot guarantee access when all permitted network paths are unavailable, and no claim of absolute anonymity or universal leak protection is made. The project does not claim Google Play approval or availability unless separately announced.

</details>

<details>
<summary><strong>Licensing and acknowledgments</strong></summary>

KProxy is a proprietary commercial application. Its original code and integrated open-source components retain their respective licensing terms.

| Component | License |
| --- | --- |
| [Xray-core](https://github.com/XTLS/Xray-core) | MPL-2.0 |
| [Hev SOCKS5 Tunnel](https://github.com/heiher/hev-socks5-tunnel) | MIT |
| [quic-go](https://github.com/quic-go/quic-go) | MIT |
| [Zstandard JNI](https://github.com/luben/zstd-jni) | BSD-2-Clause / BSD-3-Clause |

Applicable third-party notices and modified MPL source materials accompany the release. I appreciate the work of the developers and communities behind these projects.

</details>

---

<div align="center">
  <h2>KProxy</h2>
  <p>With love, Kythe.</p>
  <p><sub>© 2026 KProxy. All rights reserved, subject to applicable third-party licenses.</sub></p>
</div>
