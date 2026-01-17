# Case Study 1: URL Shortener System Design

This case study explains the **basic design of a URL Shortener system** in a simple and structured way.

---

## What is a URL Shortener?

A **URL Shortener** is a service that converts a **long URL** into a **short, unique URL** which redirects to the original long URL.

**Example:**
- Long URL: https://example.com/articles/system-design/url-shortener
- Short URL: https://short.ly/aB12x

---

## Why Do We Need a URL Shortener?

- Short URLs are easier to **share and remember**
- Saves space on **social media and messages**
- Helps with **tracking clicks and analytics**
- Improves **user experience**

---

## Requirement Clarification

### Functional Requirements
- Generate a short URL from a long URL
- Redirect short URL to the original URL
- Support high number of redirects
- Optional: URL expiration and analytics

### Non-Functional Requirements
- High availability
- Low latency
- Scalability
- Reliability

---

## Estimation and Constraints

- Read-heavy system (more redirects than creations)
- Millions of daily requests
- Short URL length should be minimal
- System must handle peak traffic efficiently

---

## Data Model Design

**URL Table:**
- id
- short_code
- long_url
- created_at
- expiry_time (optional)
- click_count

---

## API Design

### Create Short URL
POST /api/shorten

---

## High-Level Components Design

- Client (Browser / Mobile App)
- Load Balancer
- URL Shortener Service
- Database
- Cache (Redis)

---

## Detailed Components Design

- **API Service:** Handles URL creation requests
- **Redirect Service:** Handles redirection requests
- **Database:** Stores URL mappings
- **Cache:** Stores frequently accessed URLs
- **Load Balancer:** Distributes traffic evenly

---

## Identify and Resolve Bottlenecks

### Possible Bottlenecks
- Database read load
- Cache misses
- Network latency

### Solutions
- Use caching (Redis)
- Database indexing
- Horizontal scaling
- CDN for redirection

---

## Conclusion

A URL Shortener is a **simple yet scalable system** that requires careful design to handle high traffic, low latency, and high availability.
