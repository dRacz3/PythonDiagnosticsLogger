
## Example on usage
This notebook shows how to use the DiagnosticsUtility, this is the only import you will need:


```python
from diagnostics import DiagnosticsUtility
```

On object creation, pass the list of the data you want to log. 
The data is expected to be available at the same time, always log the same values


```python
du = DiagnosticsUtility(['a','b','c'])
```

Pass a dict with the proper headings for each new value. You will get an error if you try to insert a key that was not specified on object creation.


```python
for i in range(1000):
    #Just call the .log() method to append the new data. Timestamp will be created automatically
    du.log({
        'a' : i,
        'b' : i**2%15,
        'c' : i%100
    })
    # Do something..
    time.sleep(0.01)
```

Default plots can be generated like this:
(Just pass the labels for the timeseries, or the paired labels )


```python
du.generate_timeseries_plot(x_label = 'timestamp',y_labels=['a','b','c'])
du.generate_xy_plot(x_labels=['b','c'],y_labels=['a','b'])
du.clear()
```



    <div class="bk-root">
        <a href="https://bokeh.pydata.org" target="_blank" class="bk-logo bk-logo-small bk-logo-notebook"></a>
        <span id="26182f48-563e-4d2d-9b6e-6644b1aa1276">Loading BokehJS ...</span>
    </div>






<div class="bk-root">
    <div class="bk-plotdiv" id="e565c2ef-5684-40f0-b3c4-efc2a01c18e7"></div>
</div>






    <div class="bk-root">
        <a href="https://bokeh.pydata.org" target="_blank" class="bk-logo bk-logo-small bk-logo-notebook"></a>
        <span id="f8170239-02d9-4633-8a57-d8194e2fd07f">Loading BokehJS ...</span>
    </div>






<div class="bk-root">
    <div class="bk-plotdiv" id="5679d74d-89fc-421b-99f1-b6f512684b06"></div>
</div>



