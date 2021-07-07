# Machine Learning Tricks

#### Stratify two columns together

```python
conc_list = [training_data_invoices['business_code'],training_data_invoices['invoice_currency']]
X_train, X_test, Y_train, Y_test = train_test_split(X, Y, test_size=0.2, stratify = pd.concat(conc_list, axis=1), random_state=42)
```

#### Add categories which are present in validation set in Encoding
```python
# finding what are the new catagories in the validation set
diff = set(X_val['Route'])-set(route_encoder.classes_)

# adding them to the classess variable // 
for items in diff:
    route_encoder.classes_ = np.append(route_encoder.classes_,items)
```    

#### Binning using cut
```python
cut_bins = [-300,-250,-200,-150, -100, -50, 0, 50, 100, 150, 200, 250, 300]
pd.cut(Y_predict, bins=cut_bins).value_counts()
```

# JS

#### redirect invisible form
```javascript
function redirectPost(url, data) {
    var form = document.createElement('form');
    document.body.appendChild(form);
    form.method = 'post';
    form.action = url;
    for (var name in data) {
        var input = document.createElement('input');
        input.type = 'hidden';
        input.name = name;
        input.value = data[name];
        form.appendChild(input);
    }
    form.submit();
}
```
#### write response

```javascript
response.setContentType("application/json");
response.setCharacterEncoding("UTF-8");
response.getWriter().write(jsonresponse);
