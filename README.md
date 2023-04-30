# LeeJS
LeeJS - HTML and CSS templating and generating framework, with hints of data binding

HTML:
```html
<div class="container-fluid">
      <div class="row flex-nowrap" id="sortable">
            
        <div class="column">
          <div class="card">
            <div class="card-body">
              <h5 class="card-title">Column 1</h5>
              <p class="card-text">This column's width will adjust to fit the available space</p>
            </div>
          </div>
        </div>
        <div class="column">
          <div class="card">
            <div class="card-body">
              <h5 class="card-title">Column 2</h5>
              <p class="card-text">This column's width will adjust to fit the available space</p>
            </div>
          </div>
        </div>
            
      </div>
    </div>
```

LeeJS
```js
      var c = (title,text)=>{
            return div($I`.column`,
              div($I`.card`,
                div($I`.card-body`,
                  h5($I`card-title`,title),
                  p($I`card-text`,text)
                )
              )
            );
      }

      $E(
            div($I`.container-fluid`,
              div($I`#sortable.row.flex-nowrap`,
                [[`Column 1`,`This column's width will adjust to fit the available space`]
                ,[`Column 2`,`This column's width will adjust to fit the available space`]
                ].map(([title,text])=>c(title,text))
              )
            ),
      )();
```
