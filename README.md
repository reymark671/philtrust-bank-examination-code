# Mortgage Loan Calculator

A Laravel-based mortgage loan calculator application with support for fixed terms and extra repayments.

## Features

- Calculate monthly mortgage payments
- Generate detailed amortization schedules
- Handle extra repayments and loan recalculation
- Calculate effective interest rates
- RESTful API endpoints with comprehensive validation
- Docker containerization
- Unit tests for all core functionality

## Tech Stack

- PHP 8.2
- Laravel 10.x
- MySQL 8.0
- Docker
- PHPUnit for testing

## Project Structure

```
src/
├── app/
│   ├── Http/
│   │   ├── Controllers/
│   │   │   ├── LoanCalculatorController.php
│   │   │   └── API/
│   │   │       └── LoanCalculatorApiController.php
│   │   ├── Requests/
│   │   │   └── LoanCalculationRequest.php
│   │   └── Resources/
│   │       └── LoanScheduleResource.php
│   ├── Services/
│   │   ├── LoanCalculatorService.php
│   │   └── EffectiveRateCalculatorService.php
│   ├── Models/
│   │   ├── Loan.php
│   │   └── LoanSchedule.php
│   └── DTOs/
│       └── LoanSetupDTO.php
├── database/
│   └── migrations/
│       ├── create_loans_table.php
│       └── create_loan_schedules_table.php
└── tests/
    └── Feature/
        └── LoanCalculatorTest.php
```

## Setup Instructions

1. Clone the repository:
```bash
git clone git@github.com:reymark671/philtrust-bank-examination-code.git
cd mortgage-calculator
```

2. Copy environment file:
```bash
cp .env.example .env
```

3. Build and start Docker containers:
```bash
docker-compose up -d
```

4. Install dependencies:
```bash
docker-compose exec app composer install
```

5. Generate application key:
```bash
docker-compose exec app php artisan key:generate
```

6. Run migrations:
```bash
docker-compose exec app php artisan migrate
```

7. Run tests:
```bash
docker-compose exec app php artisan test
```

## API Endpoints

### Calculate Loan Schedule
```
POST /api/v1/loan/calculate
```

Request body:
```json
{
    "loan_amount": 250000,
    "annual_interest_rate": 5.5,
    "loan_term_years": 30,
    "extra_payments": [
        {
            "month": 12,
            "amount": 10000
        }
    ]
}
```

