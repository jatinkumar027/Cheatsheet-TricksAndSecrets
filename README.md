# Machine Learning Tricks

#### Stratify two columns together

```python
conc_list = [training_data_invoices['business_code'],training_data_invoices['invoice_currency']]
X_train, X_test, Y_train, Y_test = train_test_split(X, Y, test_size=0.2, stratify = pd.concat(conc_list, axis=1), random_state=42)
```

