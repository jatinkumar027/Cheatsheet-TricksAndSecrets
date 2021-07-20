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
```

# HTML

#### for a line

```html
<hr> 
```


# CSS

#### for adding a good background image easily

```css
header::before{
            background: url('https://source.unsplash.com/collection/190727/1600x900') no-repeat center center/cover;
            content: "";
            position: absolute;
            top:0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.3;
        }

```

#### grid

```css
display: grid;
grid-template-columns: 300px 100px 100px;
grid-template-columns: 300px auto 100px;
grid-template-columns: 1fr 4fr 1fr;
grid-template-columns: repeat(3, auto);

grid-column-gap: 7rem;
grid-row-gap: 1rem;
grid-gap: 2rem;

grid-template-rows: 1fr 1fr 4fr;
grid-auto-rows: 2fr;

grid-column-start: 1;
grid-column-end: 3;
grid-row-start: 1;
grid-row-end: 3;
grid-column: 1 / span 3;
grid-row: 1 / span 3;

grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
grid-template-columns: repeat(auto-fit, minmax(300px, 400px);

grid-template-areas: 
'navbar navbar navbar navbar' 
'section section section aside'
'footer footer footer footer ';
#navbar{
        grid-area: navbar;
    }
#section{
    grid-area: section;
}
#aside{
    grid-area: aside;
}
footer{
    grid-area: footer;
}

```
