---
date: 2026-05-07
tags: [project, bittorrent, roadmap, go, react]
source: ""
status: developing
---

# BitTorrent Client — 100 Day Roadmap

A 100-day roadmap to build a working BitTorrent client (Go backend + React frontend), broken into 7 phases:

- Phase 1: Programming Fundamentals (Days 1–15)
- Phase 2: Networking Fundamentals (Days 16–25)
- Phase 3: BitTorrent Protocol Deep Dive (Days 26–40)
- Phase 4: Building the Go Backend (Days 41–60)
- Phase 5: Frontend Development with React (Days 61–75)
- Phase 6: Backend API and Frontend Integration (Days 76–90)
- Phase 7: Polish and Deployment (Days 91–100)

Related: [[Getting Started with Go]], [[Introduction to Programming Concepts]]

---

### **Phase 1: Programming Fundamentals (Days 1-15)**

**Day 1: [[Introduction to Programming Concepts]]**

- Understanding what programming is and how computers execute code
- Learning about variables, data types, and basic operations
- Exploring the concept of algorithms and problem-solving

**Day 2: [[Getting Started with Go]]**

- Installing Go on your computer
- Understanding the Go workspace and project structure
- Learning about Go's philosophy and use cases

**Day 3: Go Basics - Variables and Data Types**

- Declaring and using variables in Go
- Exploring primitive data types (integers, floats, strings, booleans)
- Understanding type inference and explicit typing

**Day 4: Go Control Flow**

- Learning if-else statements and conditional logic
- Understanding loops (for loops in Go)
- Exploring switch statements

**Day 5: Go Functions**

- Defining and calling functions
- Understanding parameters and return values
- Learning about multiple return values in Go

**Day 6: Go Data Structures - Arrays and Slices**

- Understanding arrays and their limitations
- Learning about slices and slice operations
- Exploring slice manipulation and best practices

**Day 7: Go Data Structures - Maps**

- Creating and using maps (key-value pairs)
- Understanding map operations (adding, retrieving, deleting)
- Learning when to use maps vs slices

**Day 8: Go Structs**

- Defining custom data types with structs
- Understanding struct fields and methods
- Learning about struct composition

**Day 9: Go Pointers**

- Understanding memory addresses and pointers
- Learning pointer syntax and dereferencing
- Exploring pass-by-value vs pass-by-reference

**Day 10: Go Error Handling**

- Understanding Go's error handling philosophy
- Learning to return and check errors
- Exploring error creation and custom errors

**Day 11: Go Packages and Imports**

- Understanding Go's package system
- Learning to import standard library packages
- Exploring package organization and visibility rules

**Day 12: Go File I/O**

- Reading files in Go
- Writing data to files
- Understanding buffered I/O and error handling with files

**Day 13: Introduction to Concurrency Concepts**

- Understanding processes vs threads
- Learning about concurrent vs parallel execution
- Exploring why concurrency matters for network applications

**Day 14: Go Goroutines**

- Creating and running goroutines
- Understanding lightweight concurrency in Go
- Learning goroutine lifecycle and management

**Day 15: Go Channels**

- Creating and using channels for communication
- Understanding buffered vs unbuffered channels
- Learning channel direction and closing channels

---

### **Phase 2: Networking Fundamentals (Days 16-25)**

**Day 16: Introduction to Computer Networks**

- Understanding the client-server model
- Learning about IP addresses and ports
- Exploring the OSI model basics

**Day 17: TCP vs UDP Protocols**

- Understanding connection-oriented vs connectionless protocols
- Learning when to use TCP vs UDP
- Exploring protocol characteristics and trade-offs

**Day 18: HTTP Protocol Basics**

- Understanding request-response model
- Learning about HTTP methods and status codes
- Exploring headers and request/response structure

**Day 19: Go Net Package - TCP Connections**

- Creating TCP servers in Go
- Establishing TCP client connections
- Understanding connection handling and closing

**Day 20: Go Net Package - UDP Connections**

- Creating UDP servers and clients
- Understanding datagram-based communication
- Learning about UDP-specific considerations

**Day 21: Binary Data and Encoding**

- Understanding binary vs text data
- Learning about bytes and byte arrays
- Exploring encoding schemes (ASCII, UTF-8, binary)

**Day 22: Serialization and Deserialization**

- Understanding data serialization concepts
- Learning about JSON encoding/decoding in Go
- Exploring binary serialization formats

**Day 23: Network Buffers and Streaming**

- Understanding buffered I/O for network operations
- Learning to read and write streams of data
- Exploring chunked data transfer

**Day 24: HTTP Servers in Go**

- Creating basic HTTP servers using net/http
- Handling routes and request handlers
- Understanding middleware concepts

**Day 25: HTTP Clients in Go**

- Making HTTP requests from Go
- Handling responses and errors
- Understanding timeouts and connection pooling

---

### **Phase 3: BitTorrent Protocol Deep Dive (Days 26-40)**

**Day 26: Introduction to BitTorrent Protocol**

- Understanding peer-to-peer file sharing
- Learning BitTorrent's purpose and advantages
- Exploring the overall BitTorrent ecosystem

**Day 27: BitTorrent Architecture Overview**

- Understanding trackers, peers, and seeders
- Learning about swarms and torrent files
- Exploring the file sharing workflow

**Day 28: Torrent File Structure**

- Understanding .torrent file format
- Learning about Bencode encoding
- Exploring metainfo dictionary structure

**Day 29: Bencode Encoding/Decoding**

- Understanding Bencode data types
- Learning encoding rules for integers, strings, lists, dictionaries
- Practicing Bencode parsing

**Day 30: Torrent File Parsing**

- Extracting announce URL from torrent files
- Understanding info dictionary and info hash
- Learning about piece length and piece hashes

**Day 31: SHA-1 Hashing**

- Understanding cryptographic hash functions
- Learning about SHA-1 algorithm
- Exploring hash verification in BitTorrent

**Day 32: Tracker Communication Protocol**

- Understanding tracker HTTP/HTTPS requests
- Learning tracker request parameters
- Exploring tracker response format

**Day 33: Peer Discovery**

- Parsing tracker responses for peer lists
- Understanding peer ID generation
- Learning about compact peer format

**Day 34: Peer Wire Protocol Introduction**

- Understanding TCP-based peer communication
- Learning about handshake messages
- Exploring message format and types

**Day 35: BitTorrent Messages**

- Understanding choke, unchoke, interested, not interested
- Learning about have, bitfield, request messages
- Exploring piece and cancel messages

**Day 36: Piece Selection Strategies**

- Understanding rarest-first algorithm
- Learning about random first piece selection
- Exploring endgame mode

**Day 37: Download and Upload Management**

- Understanding choking algorithm
- Learning about optimistic unchoking
- Exploring download rate management

**Day 38: File Assembly and Verification**

- Understanding piece-by-piece download
- Learning piece hash verification
- Exploring file writing and assembly

**Day 39: Advanced BitTorrent Features**

- Understanding DHT (Distributed Hash Table) basics
- Learning about magnet links
- Exploring peer exchange (PEX)

**Day 40: BitTorrent Client State Management**

- Understanding client state tracking
- Learning about progress tracking
- Exploring pause/resume functionality

---

### **Phase 4: Building the Go Backend (Days 41-60)**

**Day 41: Project Setup and Structure**

- Creating Go module for your BitTorrent client
- Organizing project directory structure
- Understanding separation of concerns

**Day 42: Bencode Parser Implementation Planning**

- Designing Bencode parser interface
- Planning data structures for parsed data
- Understanding recursive parsing approach

**Day 43: Building Bencode Decoder - Part 1**

- Implementing integer decoding
- Creating string decoding logic
- Handling decoding errors

**Day 44: Building Bencode Decoder - Part 2**

- Implementing list decoding
- Creating dictionary decoding logic
- Testing decoder with sample data

**Day 45: Building Bencode Encoder**

- Implementing encoding for all data types
- Creating encoder interface
- Testing round-trip encoding/decoding

**Day 46: Torrent File Parser Implementation**

- Reading and parsing .torrent files
- Extracting metadata and info hash
- Creating torrent metadata struct

**Day 47: Tracker Client - Part 1**

- Implementing tracker request builder
- Creating URL encoding for parameters
- Understanding peer ID and port handling

**Day 48: Tracker Client - Part 2**

- Sending HTTP requests to tracker
- Parsing tracker responses
- Extracting peer list from response

**Day 49: Peer Connection Manager**

- Designing peer connection pool
- Implementing connection establishment
- Understanding concurrent connection handling

**Day 50: Handshake Implementation**

- Building handshake message structure
- Implementing handshake send/receive
- Validating handshake responses

**Day 51: Message Parser and Builder**

- Creating message type definitions
- Implementing message serialization
- Building message parsing logic

**Day 52: Bitfield Management**

- Implementing bitfield data structure
- Creating bitfield operations (set, get, clear)
- Understanding piece availability tracking

**Day 53: Piece Request Logic**

- Implementing piece request queue
- Creating request message builder
- Understanding block-level requests

**Day 54: Download Manager - Part 1**

- Designing download orchestration
- Implementing piece selection algorithm
- Creating download task distribution

**Day 55: Download Manager - Part 2**

- Implementing piece reception and validation
- Creating hash verification logic
- Understanding piece storage

**Day 56: File Writer and Assembler**

- Implementing file creation and writing
- Creating piece-to-file mapping
- Understanding multi-file torrent handling

**Day 57: Upload Manager**

- Implementing piece serving to peers
- Creating upload request handling
- Understanding bandwidth management basics

**Day 58: State Persistence**

- Designing download state storage
- Implementing resume capability
- Creating progress tracking

**Day 59: Logging and Monitoring**

- Adding structured logging to client
- Implementing download statistics
- Creating peer connection monitoring

**Day 60: Testing and Debugging Backend**

- Testing with real torrent files
- Debugging connection issues
- Validating download integrity

---

### **Phase 5: Frontend Development with React (Days 61-75)**

**Day 61: Introduction to Web Frontend**

- Understanding HTML, CSS, and JavaScript roles
- Learning about DOM and browser rendering
- Exploring modern web development

**Day 62: JavaScript Fundamentals - Part 1**

- Learning JavaScript syntax and variables
- Understanding data types and operators
- Exploring arrays and objects in JavaScript

**Day 63: JavaScript Fundamentals - Part 2**

- Learning functions and arrow functions
- Understanding scope and closures
- Exploring asynchronous JavaScript basics

**Day 64: Modern JavaScript (ES6+)**

- Learning let, const, and template literals
- Understanding destructuring and spread operator
- Exploring modules (import/export)

**Day 65: Introduction to React**

- Understanding component-based architecture
- Learning about Virtual DOM
- Exploring React's philosophy and ecosystem

**Day 66: Setting Up React Development Environment**

- Installing Node.js and npm
- Creating React app with Create React App or Vite
- Understanding project structure

**Day 67: React Components - Part 1**

- Creating functional components
- Understanding JSX syntax
- Learning component composition

**Day 68: React Props**

- Passing data to components with props
- Understanding props immutability
- Learning prop types and validation

**Day 69: React State with useState**

- Understanding component state
- Learning useState hook
- Exploring state updates and re-rendering

**Day 70: React Effects with useEffect**

- Understanding side effects in React
- Learning useEffect hook
- Exploring dependency arrays and cleanup

**Day 71: Event Handling in React**

- Handling user interactions (clicks, inputs)
- Understanding event object and synthetic events
- Learning form handling in React

**Day 72: Making API Calls from React**

- Using fetch API for HTTP requests
- Understanding async/await in React
- Learning to handle loading and error states

**Day 73: React Component Design for BitTorrent Client**

- Planning component hierarchy (Torrent List, Torrent Details, Add Torrent)
- Designing state management approach
- Understanding data flow between components

**Day 74: Styling React Components**

- Learning CSS-in-JS or CSS modules
- Understanding responsive design basics
- Creating basic UI components

**Day 75: React Testing Basics**

- Understanding component testing concepts
- Learning React Testing Library basics
- Writing simple component tests

---

### **Phase 6: Backend API and Frontend Integration (Days 76-90)**

**Day 76: REST API Concepts**

- Understanding RESTful architecture
- Learning about API endpoints and resources
- Exploring HTTP methods for CRUD operations

**Day 77: Building REST API in Go - Part 1**

- Creating HTTP handlers for torrent operations
- Implementing GET endpoints (list torrents, get status)
- Understanding JSON response formatting

**Day 78: Building REST API in Go - Part 2**

- Implementing POST endpoints (add torrent)
- Creating DELETE endpoints (remove torrent)
- Understanding request body parsing

**Day 79: CORS Configuration**

- Understanding Cross-Origin Resource Sharing
- Implementing CORS middleware in Go
- Configuring allowed origins and methods

**Day 80: WebSocket Introduction**

- Understanding real-time communication
- Learning WebSocket protocol basics
- Exploring use cases for WebSockets

**Day 81: WebSocket Implementation in Go**

- Setting up WebSocket server endpoint
- Implementing connection upgrade
- Creating message broadcasting

**Day 82: Real-time Progress Updates**

- Sending download progress via WebSocket
- Implementing peer statistics updates
- Creating event-based update system

**Day 83: React API Integration - Part 1**

- Creating API service layer in React
- Implementing torrent list fetching
- Displaying torrent data in components

**Day 84: React API Integration - Part 2**

- Implementing add torrent functionality
- Creating torrent removal feature
- Understanding state updates after API calls

**Day 85: WebSocket Integration in React**

- Setting up WebSocket client
- Handling real-time progress updates
- Updating component state from WebSocket messages

**Day 86: Advanced State Management**

- Understanding Context API or state management libraries
- Implementing global state for torrent data
- Learning state synchronization patterns

**Day 87: Error Handling and User Feedback**

- Implementing error boundaries in React
- Creating toast notifications or alerts
- Handling API errors gracefully

**Day 88: Loading States and UI Feedback**

- Creating loading spinners and skeletons
- Implementing progress bars
- Understanding optimistic UI updates

**Day 89: File Upload Handling**

- Implementing .torrent file upload in React
- Creating drag-and-drop interface
- Understanding file reading in browser

**Day 90: Integration Testing**

- Testing full workflow (add, download, remove)
- Debugging integration issues
- Validating data flow between frontend and backend

---

### **Phase 7: Polish and Deployment (Days 91-100)**

**Day 91: Application Configuration**

- Implementing configuration file support
- Creating environment-based settings
- Understanding configuration best practices

**Day 92: Security Considerations**

- Understanding basic security principles
- Implementing input validation
- Learning about rate limiting and abuse prevention

**Day 93: Performance Optimization - Backend**

- Profiling Go application
- Optimizing memory usage and goroutine management
- Understanding connection pooling

**Day 94: Performance Optimization - Frontend**

- Optimizing React component rendering
- Implementing code splitting and lazy loading
- Understanding bundle size optimization

**Day 95: Building for Production**

- Creating production builds of React app
- Compiling Go binary for target platform
- Understanding build optimization

**Day 96: Docker Containerization**

- Understanding Docker basics
- Creating Dockerfile for Go backend
- Creating Dockerfile for React frontend (with Nginx)

**Day 97: Docker Compose Setup**

- Learning Docker Compose basics
- Creating multi-container setup
- Understanding container networking

**Day 98: Deployment Options Overview**

- Understanding cloud platforms (AWS, GCP, Azure, DigitalOcean)
- Learning about VPS deployment
- Exploring containerized deployment options

**Day 99: Deploying Your Application**

- Choosing deployment platform
- Deploying backend and frontend
- Configuring domain and SSL (if applicable)

**Day 100: Documentation and Final Testing**

- Writing README with setup instructions
- Creating user documentation
- Performing end-to-end testing on deployed application