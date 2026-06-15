# Reference
## Quotes
<details><summary><code>client.Quotes.ShowQuote(ID) -> *sdk.QuoteResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &sdk.GetQuoteRequestsIDRequest{
        ID: 1,
    }
client.Quotes.ShowQuote(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Quotes.DeleteQuote(ID) -> *sdk.DeleteQuoteRequestsIDResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &sdk.DeleteQuoteRequestsIDRequest{
        ID: 1,
    }
client.Quotes.DeleteQuote(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Quotes.ListQuotes() -> *sdk.GetQuoteRequestsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Quotes.ListQuotes(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Quotes.RequestQuotes(request) -> *sdk.QuoteResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

For getting prices with benefits. 
The Quote IDs can be used later to issue a policy
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &sdk.PostQuoteRequestsRequest{
        OwnerID: "owner_id",
        Phone: "phone",
        Birthdate: sdk.MustParseDate(
            "2023-01-15",
        ),
        CarSequenceNumber: "car_sequence_number",
        CarEstimatedCost: 1.1,
    }
client.Quotes.RequestQuotes(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**ownerID:** `string` — Owner ID must be 10 digits starting with 1, 2, or 7
    
</dd>
</dl>

<dl>
<dd>

**email:** `*string` — Email address must be valid and belongs to the customer
    
</dd>
</dl>

<dl>
<dd>

**phone:** `string` — Phone number must start with 05 and be 10 digits
    
</dd>
</dl>

<dl>
<dd>

**birthdate:** `time.Time` — Birthdate in YYYY-MM-DD format
    
</dd>
</dl>

<dl>
<dd>

**carSequenceNumber:** `string` — Car sequence number must be 8 or 9 digits
    
</dd>
</dl>

<dl>
<dd>

**isOwnershipTransfer:** `*bool` — Indicates if the ownership is being transferred
    
</dd>
</dl>

<dl>
<dd>

**currentCarOwnerID:** `*string` — Required if is_ownership_transfer is true; 10 digits starting with 1,2,7
    
</dd>
</dl>

<dl>
<dd>

**carEstimatedCost:** `float64` — Estimated cost of the car
    
</dd>
</dl>

<dl>
<dd>

**carModelYear:** `*int` — Car model year between 1950 and next year
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `*time.Time` — Desired policy start date in YYYY-MM-DD. Must be between tomorrow and 28 days from today (inclusive). The platform validates this range server-side.
    
</dd>
</dl>

<dl>
<dd>

**drivers:** `[]*sdk.PostQuoteRequestsRequestDriversItem` — List of drivers for the vehicle. When provided, the sum of all driving_percentage values must equal 100, and the owner must be included among the drivers.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Policies
<details><summary><code>client.Policies.ShowPolicy(CarPolicy) -> *sdk.Policy</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Show a specific policy
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &sdk.GetPoliciesCarPolicyRequest{
        CarPolicy: 1,
    }
client.Policies.ShowPolicy(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**carPolicy:** `int` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Policies.ListPolicies() -> []*sdk.Policy</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Listing requested policies
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &sdk.GetPoliciesRequest{}
client.Policies.ListPolicies(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**quoteRequestID:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**quotePriceID:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**providerPolicyID:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**carSequenceNumber:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**newOwnerID:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**previousOwnerID:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**status:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**minPrice:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**maxPrice:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**perPage:** `*int` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Policies.IssuePolicy(request) -> *sdk.Policy</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

For issuing a new policy
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &sdk.PostPoliciesRequest{
        QuoteRequestID: 123,
        QuoteReferenceID: "550e8400-e29b-41d4-a716-446655440000",
        QuotePriceID: "550e8400-e29b-41d4-a716-446655440001",
    }
client.Policies.IssuePolicy(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**quoteRequestID:** `int` — ID of the car quote request
    
</dd>
</dl>

<dl>
<dd>

**quoteReferenceID:** `string` — Unique identifier for the quote reference ID (coming from POST /quote-requests)
    
</dd>
</dl>

<dl>
<dd>

**quotePriceID:** `string` — Unique identifier for the quote price ID that exists inside a quote item (coming from POST /quote-requests)
    
</dd>
</dl>

<dl>
<dd>

**benefits:** `[]string` — List of benefit UUIDs
    
</dd>
</dl>

<dl>
<dd>

**extraFields:** `map[string]any` — Optional free-form object with additional fields. Total JSON-encoded size must not exceed 255 characters.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## OtPs
<details><summary><code>client.OtPs.RequestOtpForQuoteVerification(request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

This endpoint sends a one-time password (OTP) to the provided email and phone number for quote verification. It should be called before creating a quote request.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &sdk.PostQuoteOtpRequest{
        Email: "someone@example.com",
        Phone: "0501234567",
        OwnerID: "1012345678",
    }
client.OtPs.RequestOtpForQuoteVerification(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**email:** `string` — Email address of the car owner
    
</dd>
</dl>

<dl>
<dd>

**phone:** `string` — Phone number starting with 05 and containing 10 digits
    
</dd>
</dl>

<dl>
<dd>

**ownerID:** `string` — National ID or Iqama ID of the car owner (10 digits)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.OtPs.RequestOtpForIssuingPolicy(request) -> error</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

This endpoint sends a one-time password (OTP). It should be called before issuing a policy.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &sdk.PostIssueOtpRequest{
        Email: "someone@example.com",
        Phone: "0501234567",
        OwnerID: "1012345678",
        QuoteRequestID: 123,
        QuoteReferenceID: "550e8400-e29b-41d4-a716-446655440000",
        QuotePriceID: "550e8400-e29b-41d4-a716-446655440001",
    }
client.OtPs.RequestOtpForIssuingPolicy(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**email:** `string` — Email address of the car owner
    
</dd>
</dl>

<dl>
<dd>

**phone:** `string` — Phone number starting with 05 and containing 10 digits
    
</dd>
</dl>

<dl>
<dd>

**ownerID:** `string` — National ID or Iqama ID of the car owner (10 digits)
    
</dd>
</dl>

<dl>
<dd>

**quoteRequestID:** `int` — ID of the car quote request
    
</dd>
</dl>

<dl>
<dd>

**quoteReferenceID:** `string` — Unique identifier for the quote reference ID (coming from POST /quote-requests)
    
</dd>
</dl>

<dl>
<dd>

**quotePriceID:** `string` — Unique identifier for the quote price ID that exists inside a quote item (coming from POST /quote-requests)
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

