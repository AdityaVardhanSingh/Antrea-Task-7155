# Antrea-Task-7155

This is a minimal Go web application using the [Gin](https://github.com/gin-gonic/gin) framework.

It demonstrates the use of a specific version of Gin (`v1.6.3`) that contains a known vulnerability related to inconsistent HTTP request interpretation, which could result in security issues like request smuggling.

---

##  What the Program Does

The program creates a simple HTTP server that listens on port 8080 and responds with `"pong"` when you visit the `/ping` endpoint.

```go
r.GET("/ping", func(c *gin.Context) {
	c.JSON(200, gin.H{"message": "pong"})
})
```


## How to Run Locally

# a. Clone the repository
    git clone https://github.com/AdityaVardhanSingh/Antrea-Task-7155
    cd Antrea-Task-7155

# b. Initialize Go module (if not already)
    go mod tidy

# c. Run the app
    go run main.go

    Then open your browser and go to: http://localhost:8080/ping


## External Dependency Used

Affected Module: github.com/gin-gonic/gin

Version Used: v1.6.3 (vulnerable)

Fixed In: v1.7.7

Purpose: Provides an HTTP router and middleware framework for building Go web servers


## Vulnerability Details

Vulnerability ID: [GO-2021-0052](https://pkg.go.dev/vuln/GO-2021-0052)

CVE: [CVE-2020-28483](https://www.cve.org/CVERecord?id=CVE-2020-28483)

Description: Inconsistent interpretation of HTTP requests could lead to request smuggling or other unexpected behavior.

