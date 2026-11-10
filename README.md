# KProxy
KProxy. Universal tool to work with HTTP, HTTPS &amp; SOCKS5 proxy servers on your Android device.

  Hi, I'm Kythe, an independent developer, and I'd like to introduce one of my biggest personal projects, KProxy.
  KProxy is an advanced Android application I've been developing for proxy management, network traffic control, connection diagnostics, and security research. What originally started as a relatively simple idea for managing proxy connections has grown into a much more complex project, combining networking technologies, protocol analysis, encryption, automation, and a collection of engineering tools within a single application.
  I wanted to create something that goes beyond the usual "enter your proxy details and press Connect" experience. Something that gives you actual control over your connections, helps you understand what's happening behind the scenes, and provides advanced functionality without making the interface unnecessarily complicated.

### Patreon: https://www.patreon.com/KytheApps/posts/kproxy-beyond-174967961

<img width="1672" height="941" alt="KProxyThumbnail" src="https://github.com/user-attachments/assets/d243d1cc-8019-4bc6-9d4d-778ed9fe476f" />

### What can KProxy do?
  The project covers quite a lot, so here's an overview of the main features and technologies I've been working on.
  Proxy connections and routing HTTP, HTTPS and SOCKS5 proxy support, customizable proxy profiles, multi-hop proxy chains with up to 12 consecutive servers, advanced traffic routing, per-application routing rules, proxy authentication, connection testing, route diagnostics, fallback proxies, automatic switching mechanisms, and configurable network behavior.
  DNS and network management local RAM-based DNS caching with TTL tracking, DNS-over-HTTPS, custom DNS resolvers, Hosts overrides, regular expression-based DNS rules, domain filtering and rewriting, DNS leak prevention mechanisms, IPv4 and IPv6 handling, connection optimization, MTU/MSS diagnostics, and advanced routing configurations.
  Traffic monitoring and analysis real-time upload and download statistics, active connection monitoring, detailed session information, per-hop latency measurements, jitter and packet loss diagnostics, connection history, traffic logging, session comparison, PCAPNG packet capture and export, network performance benchmarking, connection timing analysis, and tools for investigating unusual network behavior.
  Network engineering and diagnostics TLS handshake inspection, SNI analysis, JA3/JA4 fingerprint diagnostics, HTTP/HTTPS connectivity testing, HTTP/1.1 and HTTP/2 inspection, WebSocket analysis, STUN and WebRTC leak detection, DPI-related diagnostics, TCP connection analysis, network compatibility testing, customizable service reachability checks, and technical utilities for examining how different proxy configurations behave.
  Security and configuration protection encrypted local configuration storage, AES-256-GCM encryption, Android Keystore integration, StrongBox hardware-backed protection where available, protected configuration vaults, primary and decoy access mechanisms, Duress PIN concepts, encrypted backup and recovery, secure offline QR-based configuration transfers, and experimental steganographic backup mechanisms.
  Advanced tools and automation configurable network experiments, concurrent connection benchmarks, routing comparisons, cURL and Python replay generation, Android Quick Settings integration, application shortcuts, automated connection actions, local diagnostic reports, configuration import and export, and dedicated engineering tools for more demanding networking scenarios.
  Interface and accessibility a fully custom monochromatic interface, galaxy-inspired animations, carefully designed navigation and interactive components, detailed settings, searchable configuration categories, accessibility improvements, offline documentation, and localization across 29 languages.

<img width="1672" height="941" alt="изображение" src="https://github.com/user-attachments/assets/1265bc12-4a43-4b4f-9647-b1fcfaea8a09" />


<img width="2823" height="2944" alt="изображение" src="https://github.com/user-attachments/assets/eea4f160-8d85-446a-b15d-66a96d06af37" />


### Why am I developing this?
I enjoy building software that challenges me technically. I'm interested in understanding how things actually work, not just putting an interface on top of existing functionality.
Working on KProxy has involved a lot of research into Android networking, VPN services, TCP/IP, DNS, TLS, proxy protocols, packet processing, encryption, memory management, performance optimization, and software architecture.
And, of course, an unreasonable amount of time spent fixing tiny details that most people probably wouldn't even notice. But I think those details matter.
I've also spent a considerable amount of time on the visual side of the application. I wanted KProxy to have its own identity, with a minimalist black-and-white design, subtle gradients, smooth interactions, and a galaxy-inspired connection interface like Interstellar movie, he-h. I don't particularly like applications that have hundreds of options scattered across confusing menus. My goal is to make advanced networking functionality accessible without sacrificing the technical depth that experienced users might appreciate. I also want to be clear about one thing a proxy is not a guarantee of anonymity or complete security. Different protocols, providers, and configurations have different limitations. KProxy is being designed to provide control, transparency, and diagnostic capabilities, not to promise impossible levels of protection.

### Development and future plans
KProxy is an actively developed independent project, with the intention of becoming a premium Android application available through Google Play. I'm continuously working on its networking architecture, expanding the available tools, improving reliability, testing unusual connection scenarios, refining the interface, and making sure that new functionality integrates properly with the rest of the system. There's still a lot I want to implement, and some of the more experimental capabilities will need additional testing before they're ready for public use. I'll be using this repository to share development progress, screenshots, technical information, updates, and eventually more details about public releases. I'm not developing KProxy just to add another proxy client to the market. I'm building it because I genuinely enjoy creating sophisticated software, exploring difficult technical problems, and seeing how far I can take an idea when I'm willing to put enough time and effort into it.

With love, Kythe.
