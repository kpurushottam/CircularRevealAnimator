CircularRevealAnimator
======================

Circular reveal animation extension library of ozodrukh's <a href="https://github.com/ozodrukh/CircularReveal">CircularReveal<a/>.

Gradle line `compile 'io.github.hendraanggrian:circularrevealanimator:0.1.4'`


Simple
------

<img src="https://raw.githubusercontent.com/hendraanggrian/CircularRevealAnimator/master/artwork/sample1.gif" width="256">

```xml
<io.codetail.widget.RevealFrameLayout
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <View
        android:id="@+id/target"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>

</io.codetail.widget.RevealFrameLayout>
```

```java
CircularRevealAnimation.of(context).reveal(R.id.target, startX, startY);
```


With curve animation
--------------------

<img src="https://raw.githubusercontent.com/hendraanggrian/CircularRevealAnimator/master/artwork/sample2.gif" width="256">

```xml
<io.codetail.widget.RevealFrameLayout
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <View
        android:id="@+id/source"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>

    <View
        android:id="@+id/target"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>

</io.codetail.widget.RevealFrameLayout>
```

```java
CircularRevealAnimation.of(context).reveal(R.id.source, R.id.target);
```


Activity transition
-------------------

<img src="https://raw.githubusercontent.com/hendraanggrian/CircularRevealAnimator/master/artwork/sample3.gif" width="256">

```java
// from previous activity
CircularRevealAnimation.of(context).startActivity(new Intent(context, NextActivity.class), R.id.source);

public class NextActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_test);
        CircularRevealAnimator.of(this).onCreate(R.id.layout);
    }

    @Override
    public void onBackPressed() {
        CircularRevealAnimator.of(this).onBackPressed(R.id.layout);
    }
}
```


Requirements
------------

Minimum SDK level of API 15 (4.0+).


License
--------

    The MIT License (MIT)

    Copyright (c) 2016 Hendra Anggrianto Wijaya

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in
    all copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
    THE SOFTWARE.
