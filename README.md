**Daily Structure (30 mins):**
*   **5-10 mins: Concept Introduction/Recap:** Explain the day's topic.
*   **15-20 mins: Live Coding / Code-Along:** Demonstrate, and have them type along.
*   **5 mins: Q&A / Mini-Challenge:** Quick questions or a tiny task to reinforce.

---

**Golang for Cybersecurity - 30 Min Daily Plan (4 Weeks)**

**Week 1: Go Fundamentals & Setup**
*Goal: Get everyone running Go code and understand basic syntax.*

*   **Day 1: Why Go for Cyber? & Setup**
    *   **Concept:** Benefits of Go in cybersecurity (performance, concurrency, static binaries, cross-compilation, strong networking libraries).
    *   **Action:** Install Go, set up `GOPATH`/Go Modules. Write and run "Hello, World!".
    *   **Cyber Link:** Mention tools like Nuclei, GoPhish, etc., written in Go.
*   **Day 2: Variables, Data Types & Constants**
    *   **Concept:** `var`, `:=`, basic types (`int`, `string`, `bool`, `float64`), constants.
    *   **Action:** Declare variables, print types, simple arithmetic.
    *   **Cyber Link:** Storing an IP address (string), port number (int), vulnerability status (bool).
*   **Day 3: Control Flow - `if/else` & `switch`**
    *   **Concept:** Conditional logic.
    *   **Action:** Write `if/else` statements, simple `switch` cases.
    *   **Cyber Link:** Check if a port is open (e.g., `if port == 80`), categorizing severity levels with `switch`.
*   **Day 4: Control Flow - `for` Loops**
    *   **Concept:** Different `for` loop forms (C-style, `while`-style, `range`).
    *   **Action:** Iterate over numbers, basic slice/array (introduce briefly).
    *   **Cyber Link:** Iterating through a list of target IPs or domains.
*   **Day 5: Functions (Part 1)**
    *   **Concept:** Declaring functions, parameters, single return values.
    *   **Action:** Create simple functions (e.g., `add(a, b int) int`).
    *   **Cyber Link:** A function `isValidIP(ip string) bool`.

**Week 2: Data Structures & Pointers**
*Goal: Understand how Go organizes data and manages memory at a basic level.*

*   **Day 6: Functions (Part 2) & Packages**
    *   **Concept:** Multiple return values (especially `value, error`), importing standard packages (`fmt`, `os`, `strings`).
    *   **Action:** Function returning a result and an error. Import `strings` for a simple manipulation.
    *   **Cyber Link:** A function that tries to resolve a hostname and returns `(ip, err)`.
*   **Day 7: Arrays & Slices**
    *   **Concept:** Fixed-size arrays vs. dynamic slices, `make`, `append`, `len`, `cap`.
    *   **Action:** Create slices, append elements, iterate with `range`.
    *   **Cyber Link:** Storing a list of discovered open ports or vulnerable URLs in a slice.
*   **Day 8: Maps**
    *   **Concept:** Key-value stores, `make`, adding, retrieving, deleting, checking existence.
    *   **Action:** Create a map, store and retrieve data.
    *   **Cyber Link:** Mapping service names to port numbers (`"http": 80`), or CVEs to descriptions.
*   **Day 9: Structs**
    *   **Concept:** Defining custom data types, grouping related data.
    *   **Action:** Define a `Host` struct (e.g., `IP string`, `Ports []int`). Create instances.
    *   **Cyber Link:** Structs for `Vulnerability`, `Target`, `ScanResult`.
*   **Day 10: Pointers**
    *   **Concept:** `&` (address of), `*` (dereference). Why they are used (e.g., modifying structs in functions).
    *   **Action:** Demonstrate passing structs by value vs. by pointer to functions.
    *   **Cyber Link:** Efficiently updating a large `ScanResult` struct.

**Week 3: Go "Idioms" & Standard Library Essentials**
*Goal: Introduce more Go-specific features and useful standard library packages.*

*   **Day 11: Methods**
    *   **Concept:** Functions associated with a specific type (receiver functions).
    *   **Action:** Add a method to the `Host` struct (e.g., `func (h *Host) AddPort(port int)`).
    *   **Cyber Link:** `host.ScanPort(port int)` or `vulnerability.PrintDetails()`.
*   **Day 12: Interfaces (Intro)**
    *   **Concept:** Defining behavior, implicit satisfaction. `fmt.Stringer` as a simple example.
    *   **Action:** Define a simple interface, have a struct implement it.
    *   **Cyber Link:** An `Exporter` interface with methods like `ExportToCSV`, `ExportToJSON`.
*   **Day 13: Error Handling (In-Depth)**
    *   **Concept:** The `error` type, `errors.New()`, `fmt.Errorf()`, idiomatic error checking (`if err != nil`).
    *   **Action:** Practice returning and checking errors from functions.
    *   **Cyber Link:** Robust error handling in a network scanner or log parser.
*   **Day 14: File I/O (Reading)**
    *   **Concept:** `os.ReadFile`, `bufio.NewScanner` for line-by-line.
    *   **Action:** Read a simple text file (e.g., a list of domains).
    *   **Cyber Link:** Reading a list of targets from a file, parsing a simple log file.
*   **Day 15: File I/O (Writing)**
    *   **Concept:** `os.WriteFile`, `os.Create` and `file.WriteString()`.
    *   **Action:** Write some data to a new file.
    *   **Cyber Link:** Writing scan results or extracted IOCs to a file.

**Week 4: Basic Cyber Tooling & Concurrency Intro**
*Goal: Apply knowledge to build tiny tools and introduce Go's concurrency model.*

*   **Day 16: JSON Handling (`encoding/json`)**
    *   **Concept:** Marshaling (Go struct to JSON) and Unmarshaling (JSON to Go struct).
    *   **Action:** Convert a struct to JSON string and parse a JSON string into a struct.
    *   **Cyber Link:** Parsing API responses from threat intel feeds, Shodan, VirusTotal.
*   **Day 17: OS Interaction (`os/exec`)**
    *   **Concept:** Running external commands.
    *   **Action:** Run a simple command like `ping` or `ls`/`dir` and capture its output.
    *   **Caution:** Be very careful with user-supplied input to `os/exec` (command injection).
    *   **Cyber Link:** Wrapping command-line tools like `nmap` (carefully!), `curl`.
*   **Day 18: Basic Networking (`net` package - Dial)**
    *   **Concept:** `net.Dial` for TCP connections.
    *   **Action:** Write a simple script to check if a TCP port is open on a host.
    *   **Cyber Link:** The foundation of a port scanner.
*   **Day 19: HTTP Client (`net/http` - GET)**
    *   **Concept:** Making GET requests, reading response status and body.
    *   **Action:** Fetch the content of a webpage.
    *   **Cyber Link:** Checking for specific headers, fetching `robots.txt`, basic web enumeration.
*   **Day 20: Goroutines & Channels (Very Basic Intro)**
    *   **Concept:** `go` keyword for concurrency, `make(chan type)` for communication (simple send/receive).
    *   **Action:** Launch a simple function as a goroutine. Send a value over a channel.
    *   **Cyber Link:** Teaser for concurrent port scanning or fetching multiple URLs simultaneously.

---

**Week 5+ (Beyond the Basics - Ideas for next steps):**
*   More on Goroutines & Channels (WaitGroups, select)
*   Building a Simple Concurrent Port Scanner
*   Working with HTTP POST requests, custom headers
*   `regexp` package for pattern matching (log analysis, data extraction)
*   Building basic CLI tools with the `flag` package
*   Interacting with APIs (e.g., VirusTotal)
*   Cryptography basics with `crypto/*` packages
*   Go Modules in more depth

**Tips for the Facilitator:**
*   **Keep it Interactive:** Encourage questions. If someone is stuck, help them.
*   **Prepare Code Snippets:** Have examples ready to copy-paste or type out.
*   **Use a Shared Code Editor/Platform (Optional):** Tools like VS Code Live Share can be great.
*   **Homework (Optional & Tiny):** "Try modifying today's script to do X" (e.g., "read IPs from `ips.txt` instead of hardcoding").
*   **Focus on Understanding, Not Speed:** It's okay if some concepts take an extra day.
*   **Relate to Their Work:** Whenever possible, draw parallels to their daily cybersecurity tasks.
*   **Have Fun!** Learning a new language can be exciting.

