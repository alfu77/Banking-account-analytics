# DAX Measures

The measures below document the calculations used in the dashboard. The examples assume the main table is `ACCOUNT_DETAILS_GM` and use the field names visible in the dashboard.

## Total Accounts

```DAX
Total Accounts =
DISTINCTCOUNT('ACCOUNT_DETAILS_GM'[Account No])
```

Counts unique account numbers, avoiding double-counting when an account has multiple rows.

## Active Accounts

```DAX
Active Accounts =
CALCULATE(
    DISTINCTCOUNT('ACCOUNT_DETAILS_GM'[Account No]),
    'ACCOUNT_DETAILS_GM'[Acct Status] = "Active"
)
```

Counts unique accounts whose status is Active.

## Dormant Accounts

```DAX
Dormant Accounts =
CALCULATE(
    DISTINCTCOUNT('ACCOUNT_DETAILS_GM'[Account No]),
    'ACCOUNT_DETAILS_GM'[Acct Status] = "Dormant"
)
```

Counts unique accounts whose status is Dormant.

## Active Account %

```DAX
Active Account % =
DIVIDE(
    [Active Accounts],
    [Total Accounts],
    0
)
```

Shows the share of all accounts that are active. Format as a percentage.

## Dormant Account %

```DAX
Dormant Account % =
DIVIDE(
    [Dormant Accounts],
    [Total Accounts],
    0
)
```

Shows the share of all accounts that are dormant. Format as a percentage.

## Total Overdraft Exposure

```DAX
Total Overdraft Exposure =
CALCULATE(
    SUM('ACCOUNT_DETAILS_GM'[Available Balance]),
    'ACCOUNT_DETAILS_GM'[Available Balance] < 0
)
```

Adds only negative available balances and reverses the sign so that overdraft exposure is displayed as a positive amount.

## Referenced Fields

- `Account No`
- `Acct Status`
- `Available Balance`
- `Name`
- `Branch Name`
- `Ccy`
- `Account Officer`
- `Product`

