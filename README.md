# Blanket
**Blanket** is a simple library to help you **bind your views** and use a **fluent interface** to access their methods.

**Why Create Blanket?** The main goal to create **Blanket** has an [issue #100](https://github.com/JakeWharton/butterknife/issues/100) from the great [*Butterknife*](http://jakewharton.github.io/butterknife/) library. Basically, I need to convert a *android.application* to *android.library*, but the project has developed with *Butterknife* and I wanted a good code. Then I create **Blanket** to solve the bind problem and maintain my code elegant.

## Download
**Step 1.** Add it in your root *build.gradle* at the end of repositories:
```gradle
allprojects {
	repositories {
		maven { url "https://jitpack.io" }
	}
}
```
**Step 2.** Add the dependency
```gradle
dependencies {
	compile 'com.github.marcellogalhardo:Blanket:0.1.0'
}
```
That's it!

## Using

### Simple Usage

```android
Blanket blanket = Blanket.with(this);
blanket.textView(R.id.textviewHelloWorld)
    .text("teste")
    .textColor(ContextCompat.getColor(this, R.color.colorAccent))
    .textSize(50)
    .allCaps(true)
    .enabled(true);
```

Container Support:
- Activity;
- Fragment;
- Dialog.

View Support:
- Button;
- CheckBox;
- CompoundButton;
- EditText;
- ImageButton;
- ImageView;
- ProgressBar;
- RadioButton;
- SeekBar;
- Switch;
- TextView;
- ToggleButton;
- View.

### BlanketBag Usage
```android
BlanketBag.wrap(new EditText()) // or a reference
    .text("teste")
    .textColor(ContextCompat.getColor(this, R.color.colorAccent))
    .textSize(50)
    .allCaps(true)
    .enabled(true);
```

### ViewBinder Usage
```android
ViewBinder viewBinder = ViewBinderFactory.create(this);
TextView textView = viewBinder.findById(R.id.textView);
```

## Credits
- [Thiago Rocha](https://github.com/thiagokimo).
- [Danilo Prado](https://github.com/DanPrado).

## License

Copyright 2016 Marcello Galhardo

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License.
You may obtain a copy of the License at: [here](http://www.apache.org/licenses/LICENSE-2.0).

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and
limitations under the License.
