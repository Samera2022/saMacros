# saMacros JavaScript 鑴氭湰寮€鍙戞寚鍗?

娆㈣繋鏉ュ埌 saMacros 鑴氭湰寮€鍙戞寚鍗楋紒鏈寚鍗楀皢甯姪鎮ㄥ垱寤哄己澶х殑 JavaScript 鑴氭湰鏉ユ墿灞?saMacros 鐨勫姛鑳姐€?

## 鐩綍

1. [姒傝堪](#姒傝堪)
2. [鑴氭湰缁撴瀯](#鑴氭湰缁撴瀯)
3. [鍏冩暟鎹０鏄嶿(#鍏冩暟鎹０鏄?
4. [鑴氭湰 API 鍙傝€僝(#鑴氭湰-api-鍙傝€?
5. [浜嬩欢绯荤粺](#浜嬩欢绯荤粺)
6. [鍙敤浜嬩欢](#鍙敤浜嬩欢)
7. [鑴氭湰渚濊禆](#鑴氭湰渚濊禆)
8. [鍘熺敓璁块棶](#鍘熺敓璁块棶)
9. [閿欒澶勭悊](#閿欒澶勭悊)
10. [鏈€浣冲疄璺礭(#鏈€浣冲疄璺?
11. [绀轰緥](#绀轰緥)

## 姒傝堪

saMacros 閫氳繃 GraalVM 鐨?Polyglot 寮曟搸鏀寔 JavaScript 鑴氭湰銆傝剼鏈彲浠ワ細

- 鐩戝惉骞跺搷搴斿簲鐢ㄤ簨浠?
- 妯℃嫙榧犳爣鍜岄敭鐩樻搷浣?
- 璁块棶搴旂敤閰嶇疆
- 鎹曡幏灞忓箷鍍忕礌棰滆壊
- 鍚戠敤鎴锋樉绀洪€氱煡
- 渚濊禆鍏朵粬鑴氭湰骞惰繘琛屽畬鏁寸殑渚濊禆绠＄悊
- 鍦ㄧ敤鎴疯鍙殑鎯呭喌涓嬶紝鑾峰彇鍘熺敓璁块棶鏉冮檺浠ユ墽琛岄珮绾т换鍔?

## 鑴氭湰缁撴瀯

姣忎釜鑴氭湰蹇呴』鍖呭惈锛?

1. **鍏冩暟鎹０鏄?* - 鑴氭湰鐨勪俊鎭?
2. **浠ｇ爜閫昏緫** - 浜嬩欢澶勭悊鍣ㄥ拰鍔熻兘瀹炵幇
3. **鍙€夌殑鍒濆鍖?* - 鑴氭湰鍔犺浇鏃惰繍琛岀殑璁剧疆浠ｇ爜

### 鏈€灏忚剼鏈ず渚?

```javascript
const registry_name = 'my_script';
const display_name = '鎴戠殑鑴氭湰';
const version = '1.0.0';
const author = '浣犵殑鍚嶅瓧';
const description = '鎴戠殑鑴氭湰鏄仛浠€涔堢殑';
const available_version = '1.0.0~2.3.*';
const requireNativeAccess = false; // 鍙€?
const requireNativeAccessDescription = "..." // 鍙€夛紝姝ゅ瓧绗︿覆灏嗘樉绀哄湪璀﹀憡绐楀彛涓?
const soft_dependencies = []; // 鍙€?
const hard_dependencies = []; // 鍙€?

// 鍙€夛細娉ㄥ唽浜嬩欢鐩戝惉鍣?
mm.on('io.github.samera2022.samacros.api.event.events.OnAppLaunchedEvent', (event) => {
    mm.log('鎴戠殑鑴氭湰宸插垵濮嬪寲锛?);
});
```

## 鍏冩暟鎹０鏄?

鎵€鏈夎剼鏈繀椤诲湪鏂囦欢椤堕儴浠ュ叏灞€鍙橀噺鐨勫舰寮忓０鏄庝互涓嬪厓鏁版嵁锛?

### 蹇呴渶瀛楁

| 瀛楁 | 绫诲瀷 | 鎻忚堪 |
|------|------|------|
| `registry_name` | string | 鑴氭湰鐨勫敮涓€鏍囪瘑绗︺€傜敤浜庝緷璧栧拰鍐呴儴寮曠敤銆傚湪鎵€鏈夎剼鏈腑蹇呴』鍞竴銆?|
| `display_name` | string | 鍦?UI 涓樉绀虹殑浜虹被鍙鍚嶇О銆?|
| `version` | string | 鑴氭湰鐨勫綋鍓嶇増鏈紙鎺ㄨ崘浣跨敤璇箟鐗堟湰鎺у埗锛夈€?|
| `author` | string | 浣滆€呭悕绉般€?|
| `description` | string | 鑴氭湰鍔熻兘鐨勭畝瑕佹弿杩般€?|
| `available_version` | string | 姝よ剼鏈吋瀹圭殑 saMacros 鐗堟湰 (渚嬪, "2.0.0", "2.x", "1.0.0 ~ 2.0.0")銆備娇鐢?"*" 琛ㄧず鍏煎鎵€鏈夌増鏈€?|

### 鍙€夊瓧娈?

| 瀛楁 | 绫诲瀷 | 鎻忚堪 |
|------|------|------|
| `soft_dependencies` | string[] | 鑴氭湰 `register_name` 鐨勬暟缁勶紝杩欎簺鑴氭湰鑳藉寮哄姛鑳戒絾涓嶆槸蹇呴渶鐨勩€?|
| `hard_dependencies` | string[] | 鑴氭湰 `register_name` 鐨勬暟缁勶紝杩欎簺鑴氭湰鏄繀闇€鐨勩€傚鏋滅己澶憋紝姝よ剼鏈皢琚鐢ㄣ€?|
| `requires_native_access` | boolean | 濡傛灉鑴氭湰闇€瑕佸師鐢熺郴缁熻闂潈闄愶紝璁剧疆涓?`true`銆?*闇€瑕佺敤鎴锋槑纭壒鍑嗐€?* |
| `native_access_description` | string | 娓呮鍦拌В閲婁负浠€涔堥渶瑕佸師鐢熻闂潈闄愩€傝繖浼氬湪瀹夊叏鎻愮ず涓樉绀虹粰鐢ㄦ埛銆?|

### 鍏冩暟鎹ず渚?

```javascript
// 鍩烘湰鑴氭湰
const registry_name = 'simple_script';
const display_name = '绠€鍗曡剼鏈?;
const version = '1.0.0';
const author = '寮犱笁';
const description = '璁板綍浜嬩欢鐨勭畝鍗曡剼鏈?;
const available_version = '1.0.0';

// 甯︽湁渚濊禆鐨勮剼鏈?
const registry_name = 'advanced_script';
const display_name = '楂樼骇鑴氭湰';
const version = '1.0.0';
const author = '鏉庡洓';
const description = '渚濊禆鍏朵粬鑴氭湰鐨勮剼鏈?;
const available_version = '1.0.0';
const soft_dependencies = ['helper_script'];
const hard_dependencies = ['core_dependency'];

// 闇€瑕佸師鐢熻闂殑鑴氭湰
const registry_name = 'system_script';
const display_name = '绯荤粺闆嗘垚鑴氭湰';
const version = '1.0.0';
const author = '绠＄悊鍛?;
const description = '涓庣郴缁?API 浜や簰';
const available_version = '1.0.0';
const requires_native_access = true;
const native_access_description = '闇€瑕佽闂郴缁?API 浠ヨ幏寰楅珮绾у姛鑳?;
```

## 鑴氭湰 API 鍙傝€?

鑴氭湰 API 閫氳繃鍏ㄥ眬 `mm` 瀵硅薄杩涜璁块棶銆傝瀵硅薄鎻愪緵涓?saMacros 浜や簰鐨勬柟娉曘€?

### `mm.on(eventClassName, callback)`

娉ㄥ唽鐗瑰畾浜嬩欢绫诲瀷鐨勭洃鍚櫒銆?

**鍙傛暟锛?*
- `eventClassName` (string): 浜嬩欢绫荤殑瀹屽叏闄愬畾鍚?
- `callback` (function): 浜嬩欢瑙﹀彂鏃舵墽琛岀殑鍑芥暟

**绀轰緥锛?*
```javascript
mm.on('io.github.samera2022.samacros.api.event.events.OnAppLaunchedEvent', (event) => {
    mm.log('搴旂敤鍚姩浜? ' + new Date(event.getTimestamp()));
});
```

### `mm.getContext()`

杩斿洖鑴氭湰涓婁笅鏂囧璞′互璁块棶搴旂敤鍔熻兘銆?

**杩斿洖锛?* 鍏锋湁浠ヤ笅鏂规硶鐨?ScriptContext 瀵硅薄锛?

#### `simulate(action)`
閫氳繃璋冪敤鍔ㄤ綔鐨?`perform()` 鏂规硶妯℃嫙榧犳爣鎴栭敭鐩樻搷浣溿€?
- **鍙傛暟锛?* `action` (IMouseAction) - 瑕佹ā鎷熺殑鍔ㄤ綔
- **杩斿洖锛?* void
- **瀹炵幇锛?* 濮旀墭缁欏姩浣滅殑 perform() 鏂规硶锛屽寘鍚敊璇鐞?

#### `getPixelColor(x, y)`
浣跨敤 Java Robot 鑾峰彇灞忓箷鍧愭爣澶勫儚绱犵殑 RGB 棰滆壊銆?
- **鍙傛暟锛?* 
  - `x` (int) - 灞忓箷涓婄殑 X 鍧愭爣
  - `y` (int) - 灞忓箷涓婄殑 Y 鍧愭爣
- **杩斿洖锛?* 鍖呭惈 RGB 鍊肩殑 Color 瀵硅薄锛屽け璐ユ椂杩斿洖 null
- **瀹炵幇锛?* 浣跨敤 `java.awt.Robot.getPixelColor()` 鎹曡幏灞忓箷鍍忕礌

#### `showToast(title, message)`
鍚戠敤鎴锋樉绀虹郴缁熸墭鐩橀€氱煡銆?
- **鍙傛暟锛?*
  - `title` (string) - 閫氱煡鏍囬
  - `message` (string) - 閫氱煡娑堟伅
- **杩斿洖锛?* void
- **瀹炵幇锛?* 浣跨敤 SystemTray 鍜?TrayIcon 鏄剧ず閫氱煡銆傚鏋滈渶瑕侊紝浼氬垱寤轰复鏃舵墭鐩樺浘鏍囥€傚鏋滀笉鏀寔鎵樼洏锛屽垯鍥為€€鍒版帶鍒跺彴杈撳嚭銆?

#### `getAppConfig()`
璁块棶搴旂敤绋嬪簭閰嶇疆璁剧疆銆?
- **杩斿洖锛?* IConfig 瀵硅薄锛屽寘鍚柟娉曪細`getBoolean()`銆乣getInt()`銆乣getDouble()`銆乣getString()`銆乣getKeyMap()`

**绀轰緥锛?*
```javascript
const context = mm.getContext();

// 鏄剧ず閫氱煡
context.showToast('浣犲ソ', '鑴氭湰姝ｅ湪杩愯锛?);

// 鑾峰彇鍧愭爣 (100, 100) 澶勭殑鍍忕礌棰滆壊
const color = context.getPixelColor(100, 100);
mm.log('(100,100) 澶勭殑棰滆壊: R=' + color.getRed() + ' G=' + color.getGreen() + ' B=' + color.getBlue());

// 妯℃嫙鍔ㄤ綔锛堥渶瑕?IMouseAction 瀵硅薄锛?
// context.simulate(someAction);

// 璁块棶閰嶇疆
const config = context.getAppConfig();
mm.log('娣辫壊妯″紡宸插惎鐢? ' + config.getBoolean('enable_dark_mode'));
```

#### v2.1 鏂板锛氭墿灞曚笂涓嬫枃 API

**绯荤粺淇℃伅锛?*
```javascript
const system = context.getSystemInfo();
const scale = system.getScale();  // [scaleX, scaleY]
mm.log('DPI 缂╂斁: ' + scale[0] + 'x' + scale[1]);
mm.log('娣辫壊妯″紡: ' + system.isSystemDarkMode());
mm.log('鎿嶄綔绯荤粺: ' + system.getOSName());
mm.log('Java 鐗堟湰: ' + system.getJavaVersion());
mm.log('绯荤粺璇█: ' + system.getSystemLanguage());
```

**灞忓箷淇℃伅锛?*
```javascript
const screen = context.getScreenInfo();
mm.log('灞忓箷: ' + screen.getWidth() + 'x' + screen.getHeight());
mm.log('鏄剧ず鍣ㄦ暟閲? ' + screen.getScreenCount());

// 澶氭樉绀哄櫒鍧愭爣杞崲
const origin = screen.getVirtualOrigin();
const normalized = screen.normalizeToVirtualOrigin(1920, 1080);
```

**瀹忕姸鎬侊細**
```javascript
const macro = context.getMacroInfo();
mm.log('褰曞埗涓? ' + macro.isRecording());
mm.log('鎾斁涓? ' + macro.isPlaying());
mm.log('宸叉殏鍋? ' + macro.isPaused());
mm.log('鍔ㄤ綔鏁? ' + macro.getActionsCount());
```

**鍥介檯鍖栵細**
```javascript
const i18n = context.getI18n();
mm.log('璇█: ' + i18n.getCurrentLanguage());
if (i18n.hasKey('main_frame')) {
    mm.log('鏍囬: ' + i18n.get('main_frame'));
}
```

**榧犳爣淇℃伅锛?*
```javascript
const mouse = context.getMouseInfo();
const pos = mouse.getPosition();
if (pos != null) {
    mm.log('榧犳爣浣嶇疆: (' + pos.x + ', ' + pos.y + ')');
}
```

### `mm.log(message)`

灏嗘秷鎭墦鍗板埌鎺у埗鍙帮紝甯︽湁 `[Script]` 鍓嶇紑銆?

**鍙傛暟锛?*
- `message` (string): 瑕佽褰曠殑娑堟伅

**绀轰緥锛?*
```javascript
mm.log('杩欐槸涓€鏉℃棩蹇楁秷鎭?);
// 杈撳嚭: [Script] 杩欐槸涓€鏉℃棩蹇楁秷鎭?
```

### `mm.cleanup()`

鍦ㄨ剼鏈绂佺敤鏃惰嚜鍔ㄨ皟鐢ㄣ€傝鐩栨鏂规硶浠ユ竻鐞嗚祫婧愩€?

## 浜嬩欢绯荤粺

saMacros 浜嬩欢鍏佽鑴氭湰瀵瑰悇绉嶅簲鐢ㄧ姸鎬佸拰鐢ㄦ埛鎿嶄綔鍋氬嚭鍙嶅簲銆備簨浠堕伒寰彂甯?璁㈤槄妯″紡銆?

### 浜嬩欢鐢熷懡鍛ㄦ湡

1. 搴旂敤鍒涘缓浜嬩欢
2. 浜嬩欢閫氳繃浜嬩欢绯荤粺鍒嗘淳
3. 鎵€鏈夊凡娉ㄥ唽鐨勭洃鍚櫒閮芥敹鍒伴€氱煡
4. 瀵逛簬鍙彇娑堢殑浜嬩欢锛岃剼鏈彲浠ラ樆姝㈣繘涓€姝ョ殑澶勭悊

### 浜嬩欢瀵硅薄鏂规硶

鎵€鏈変簨浠堕兘鏈夛細
- `getTimestamp()` - 杩斿洖浜嬩欢鍒涘缓鐨勬椂闂达紙姣锛?

鍙彇娑堜簨浠舵湁锛?
- `isCancelled()` - 妫€鏌ヤ簨浠舵槸鍚﹀凡琚彇娑?
- `setCancelled(boolean)` - 鍙栨秷浜嬩欢锛堥槻姝㈤粯璁ゆ搷浣滐級

## 鍙敤浜嬩欢

### 搴旂敤鐢熷懡鍛ㄦ湡浜嬩欢

#### `OnAppLaunchedEvent`
搴旂敤鍚姩鏃惰Е鍙戙€?

**灞炴€э細**
- `getApplicationVersion()` - 鑾峰彇 saMacros 鐗堟湰
- `getJavaVersion()` - 鑾峰彇 Java 鐗堟湰

**绀轰緥锛?*
```javascript
mm.on('io.github.samera2022.samacros.api.event.events.OnAppLaunchedEvent', (event) => {
    mm.log('搴旂敤鐗堟湰: ' + event.getApplicationVersion());
    mm.log('Java 鐗堟湰: ' + event.getJavaVersion());
});
```

### 褰曞埗浜嬩欢

#### `BeforeRecordStartEvent`
褰曞埗寮€濮嬪墠瑙﹀彂銆傚彲鍙栨秷銆?

**灞炴€э細**
- `isCancelled()` - 妫€鏌ュ綍鍒舵槸鍚﹁闃绘
- `setCancelled(boolean)` - 闃绘褰曞埗寮€濮?

**绀轰緥锛?*
```javascript
mm.on('io.github.samera2022.samacros.api.event.events.BeforeRecordStartEvent', (event) => {
    mm.log('鍗冲皢寮€濮嬪綍鍒?);
});
```

#### `AfterRecordStopEvent`
褰曞埗鍋滄鍚庤Е鍙戙€?

**灞炴€э細**
- `getActionsCount()` - 璁板綍鐨勬搷浣滄暟

**绀轰緥锛?*
```javascript
mm.on('io.github.samera2022.samacros.api.event.events.AfterRecordStopEvent', (event) => {
    mm.log('褰曞埗浜?' + event.getActionsCount() + ' 涓搷浣?);
});
```

#### `OnInputCapturedEvent`
褰曞埗鏈熼棿鎹曡幏杈撳叆锛堥紶鏍囨垨閿洏锛夋椂瑙﹀彂銆傚彲鍙栨秷銆?

**灞炴€э細**
- `getInputType()` - 杈撳叆绫诲瀷锛?=榧犳爣鎸変笅, 2=榧犳爣閲婃斁, 3=婊氳疆, 10=閿洏鎸変笅, 11=閿洏閲婃斁锛?
- `getKeyCode()` - 閿爜锛堥敭鐩樹簨浠讹級
- `getX()` - X 鍧愭爣锛堥紶鏍囦簨浠讹級
- `getY()` - Y 鍧愭爣锛堥紶鏍囦簨浠讹級
- `getDelay()` - 璺濈涓婃鎿嶄綔鐨勬椂闂达紙姣锛?
- `isCancelled()` / `setCancelled()` - 鍙栨秷杈撳叆鎹曡幏

**绀轰緥锛?*
```javascript
mm.on('io.github.samera2022.samacros.api.event.events.OnInputCapturedEvent', (event) => {
    if (event.getInputType() === 1) { // 榧犳爣鎸変笅
        mm.log('榧犳爣鍦?(' + event.getX() + ', ' + event.getY() + ') 澶勬寜涓?);
    }
});
```

### 鍥炴斁浜嬩欢

#### `BeforePlaybackStartEvent`
瀹忓洖鏀惧紑濮嬪墠瑙﹀彂銆傚彲鍙栨秷銆?

**灞炴€э細**
- `getMacroData()` - 灏嗚鎾斁鐨勬搷浣滃垪琛?
- `getRepeatCount()` - 瀹忓皢閲嶅鐨勬鏁?
- `isCancelled()` / `setCancelled()` - 鍙栨秷鍥炴斁

**绀轰緥锛?*
```javascript
mm.on('io.github.samera2022.samacros.api.event.events.BeforePlaybackStartEvent', (event) => {
    mm.log('寮€濮嬪洖鏀撅紝閲嶅 ' + event.getRepeatCount() + ' 娆?);
});
```

#### `BeforeStepExecuteEvent`
鍦ㄦ墽琛屾瘡涓崟鐙殑鎿嶄綔鍓嶈Е鍙戙€傚彲鍙栨秷銆?

**灞炴€э細**
- `getAction()` - 鍗冲皢鎵ц鐨勬搷浣?
- `getActionIndex()` - 鎿嶄綔鐨勭储寮?
- `isCancelled()` / `setCancelled()` - 璺宠繃姝ゆ搷浣?

**绀轰緥锛?*
```javascript
mm.on('io.github.samera2022.samacros.api.event.events.BeforeStepExecuteEvent', (event) => {
    if (event.getActionIndex() % 10 === 0) {
        mm.log('鎵ц鎿嶄綔 ' + event.getActionIndex());
    }
});
```

#### `AfterStepExecuteEvent`
姣忎釜鎿嶄綔鎵ц鍚庤Е鍙戙€?

**灞炴€э細**
- `getAction()` - 宸叉墽琛岀殑鎿嶄綔
- `getActionIndex()` - 鎿嶄綔鐨勭储寮?

**绀轰緥锛?*
```javascript
mm.on('io.github.samera2022.samacros.api.event.events.AfterStepExecuteEvent', (event) => {
    // 姣忎釜鎿嶄綔鐨勮嚜瀹氫箟寤惰繜閫昏緫
});
```

#### `OnLoopCompleteEvent`
褰撳惊鐜凯浠ｅ畬鎴愭椂瑙﹀彂锛堝畯鐨勪竴娆″畬鏁存挱鏀撅級銆?

**灞炴€э細**
- `getLoopNumber()` - 鍒氬垰瀹屾垚鐨勮凯浠?
- `getTotalLoops()` - 杩唬鎬绘暟

**绀轰緥锛?*
```javascript
mm.on('io.github.samera2022.samacros.api.event.events.OnLoopCompleteEvent', (event) => {
    mm.log('瀹屾垚寰幆 ' + event.getLoopNumber() + '/' + event.getTotalLoops());
});
```

#### `OnPlaybackAbortedEvent`
鐢ㄦ埛鎴栬剼鏈腑姝㈠洖鏀炬椂瑙﹀彂銆?

**绀轰緥锛?*
```javascript
mm.on('io.github.samera2022.samacros.api.event.events.OnPlaybackAbortedEvent', (event) => {
    mm.log('鍥炴斁宸蹭腑姝?);
});
```

### 鏂囦欢鎿嶄綔浜嬩欢

#### `OnMacroSaveEvent`
灏嗗畯淇濆瓨鍒版枃浠舵椂瑙﹀彂銆?

**灞炴€э細**
- `getMacroName()` - 姝ｅ湪淇濆瓨鐨勫畯鐨勫悕绉?
- `getFilePath()` - 淇濆瓨瀹忕殑璺緞

**绀轰緥锛?*
```javascript
mm.on('io.github.samera2022.samacros.api.event.events.OnMacroSaveEvent', (event) => {
    mm.log('瀹忓凡淇濆瓨: ' + event.getMacroName());
});
```

#### `OnMacroLoadEvent`
浠庢枃浠跺姞杞藉畯鏃惰Е鍙戙€?

**灞炴€э細**
- `getMacroName()` - 鍔犺浇鐨勫畯鐨勫悕绉?
- `getFilePath()` - 鍔犺浇鐨勫畯鐨勮矾寰?

**绀轰緥锛?*
```javascript
mm.on('io.github.samera2022.samacros.api.event.events.OnMacroLoadEvent', (event) => {
    mm.log('瀹忓凡鍔犺浇: ' + event.getMacroName());
});
```

### 閰嶇疆浜嬩欢

#### `OnConfigChangedEvent`
搴旂敤閰嶇疆鏇存敼鏃惰Е鍙戙€?

**灞炴€э細**
- `getChangedKey()` - 鏇存敼鐨勯厤缃敭
- `getNewValue()` - 閰嶇疆鐨勬柊鍊?

**绀轰緥锛?*
```javascript
mm.on('io.github.samera2022.samacros.api.event.events.OnConfigChangedEvent', (event) => {
    if ('dark_mode' === event.getChangedKey()) {
        mm.log('娣辫壊妯″紡鏇存敼涓? ' + event.getNewValue());
    }
});
```

#### `OnMenuInitEvent`
UI 鑿滃崟鍒濆鍖栨椂瑙﹀彂銆?

**绀轰緥锛?*
```javascript
mm.on('io.github.samera2022.samacros.api.event.events.OnMenuInitEvent', (event) => {
    mm.log('鑿滃崟宸插垵濮嬪寲');
});
```

### 鍏朵粬浜嬩欢

#### `OnActionAddedEvent`
鎿嶄綔琚褰?娣诲姞鍒板畯鏃惰Е鍙戙€?

**灞炴€э細**
- `getAction()` - 娣诲姞鐨勬搷浣?

#### `OnTooltipDisplayEvent`
鍗冲皢鏄剧ず宸ュ叿鎻愮ず鏃惰Е鍙戙€傚彲鍙栨秷銆?

**灞炴€э細**
- `getTooltipText()` - 宸ュ叿鎻愮ず鐨勬枃鏈?
- `setTooltipText(String)` - 淇敼宸ュ叿鎻愮ず鏂囨湰

## 鑴氭湰渚濊禆

鑴氭湰鍙互渚濊禆鍏朵粬鑴氭湰鏉ュ叡浜姛鑳藉苟閬垮厤浠ｇ爜閲嶅銆?

### 澹版槑渚濊禆

```javascript
// 杞緷璧栵細寰堝ソ鏈夛紝浣嗗彲閫?
const soft_dependencies = ['helper_script', 'utils_script'];

// 纭緷璧栵細鑴氭湰宸ヤ綔鎵€闇€
const hard_dependencies = ['core_dependency'];
```

### 渚濊禆瑙勫垯

- **纭緷璧?*锛氬鏋滅己灏戜换浣曠‖渚濊禆鎴栫‖渚濊禆琚鐢紝鑴氭湰灏嗘棤娉曞惎鐢?
- **杞緷璧?*锛氱己灏戣蒋渚濊禆涓嶄細闃绘鑴氭湰杩愯锛屼絾鍔熻兘鍙兘鏈夐檺
- **寰幆渚濊禆**锛氫笉鍏佽銆傜郴缁熷皢妫€娴嬪苟鎶ュ憡寰幆渚濊禆闂
- **鐗堟湰妫€鏌?*锛氫緷璧栭€氳繃 `registry_name` 杩涜鍖归厤

### 渚濊禆鏈€浣冲疄璺?

1. 浠呭湪缁濆蹇呰鏃朵娇鐢ㄧ‖渚濊禆
2. 鏂囨。鍖栨瘡涓緷璧栭渶瑕佷粈涔堝姛鑳?
3. 鍦ㄨ繍琛屾椂妫€鏌ュ彲閫夊姛鑳芥槸鍚﹀彲鐢?
4. 浣跨敤鎻忚堪鍏剁洰鐨勭殑鏈夋剰涔夌殑渚濊禆鍚嶇О

## 鍘熺敓璁块棶

鏌愪簺鑴氭湰鍙兘闇€瑕佽闂秴鍑哄畨鍏ㄨ剼鏈?API 鑼冨洿鐨?Java 绫诲拰绯荤粺 API銆?

### 璇锋眰鍘熺敓璁块棶

```javascript
const requires_native_access = true;
const native_access_description = '闇€瑕佽闂郴缁熷壀璐存澘浠ヨ幏寰楅珮绾у姛鑳?;
```

### 浣跨敤鍘熺敓璁块棶

鑾峰緱鎵瑰噯鍚庯紝鑴氭湰鍙互璁块棶 Java 绫伙細

```javascript
// 璁块棶 Java 绫?
const File = Java.type('java.io.File');
const System = Java.type('java.lang.System');

// 浣跨敤 Java API
const home = System.getProperty('user.home');
mm.log('涓荤洰褰? ' + home);
```

### 瀹夊叏鑰冭檻

- 鐢ㄦ埛蹇呴』鏄庣‘鎵瑰噯鍘熺敓璁块棶
- 绠＄悊鍛樺彲浠ュ垪鍏ヨ剼鏈?浣滆€呯櫧鍚嶅崟
- 璇锋眰鍘熺敓璁块棶鐨勮剼鏈皢鍚戠敤鎴锋樉绀鸿鍛?
- 浠呭湪鐪熸蹇呰鏃惰姹傚師鐢熻闂?

## 閿欒澶勭悊

鍋ュ．鐨勯敊璇鐞嗗彲纭繚鑴氭湰涓嶄細瀵艰嚧搴旂敤宕╂簝銆?

### Try-Catch 鍧?

```javascript
mm.on('io.github.samera2022.samacros.api.event.events.BeforePlaybackStartEvent', (event) => {
    try {
        // 鏈夐闄╃殑鎿嶄綔
        const data = event.getMacroData();
        if (data.length === 0) {
            throw new Error('娌℃湁鍙敤鐨勫畯鏁版嵁');
        }
    } catch (error) {
        mm.log('閿欒: ' + error.message);
        event.setCancelled(true); // 闃绘鍥炴斁
    }
});
```

### 楠岃瘉妯″紡

```javascript
function validateInput(value, expectedType) {
    if (typeof value !== expectedType) {
        throw new TypeError('鏈熸湜 ' + expectedType + '锛屽緱鍒?' + typeof value);
    }
    return value;
}

mm.on('io.github.samera2022.samacros.api.event.events.OnInputCapturedEvent', (event) => {
    try {
        const inputType = validateInput(event.getInputType(), 'number');
        // 澶勭悊楠岃瘉鐨勮緭鍏?
    } catch (error) {
        mm.log('楠岃瘉閿欒: ' + error.message);
    }
});
```

## 鏈€浣冲疄璺?

### 1. 淇濇寔鑴氭湰涓撴敞
姣忎釜鑴氭湰搴旇鏈夊崟涓€銆佹槑纭畾涔夌殑鐩殑銆?

### 2. 浣跨敤鏈夋剰涔夌殑鍚嶇О
```javascript
const registry_name = 'screenshot_capture_tool';  // 濂?
const registry_name = 'tool1';                    // 閬垮厤
```

### 3. 璁板綍閲嶈浜嬩欢
```javascript
mm.log('鑴氭湰宸插垵濮嬪寲');
mm.log('澶勭悊 ' + actionCount + ' 涓搷浣?);
mm.log('鎿嶄綔鎴愬姛瀹屾垚');
```

### 4. 澶勭悊杈圭晫鎯呭喌
```javascript
if (event.getActionsCount && event.getActionsCount() === 0) {
    mm.log('璀﹀憡锛氭病鏈夋搷浣滃彲澶勭悊');
    return;
}
```

### 5. 娓呯悊璧勬簮
```javascript
mm.on('io.github.samera2022.samacros.api.event.events.OnAppLaunchedEvent', (event) => {
    // 鍒濆鍖?
    globalResources = {};
});

// 绂佺敤鏃舵竻鐞?
function onScriptDisabled() {
    if (globalResources) {
        // 娓呯悊浠ｇ爜
        globalResources = null;
    }
}
```

### 6. 涓鸿剼鏈増鏈寲
浣跨敤璇箟鐗堟湰鎺у埗锛圡AJOR.MINOR.PATCH锛夛細
```javascript
const version = '1.0.0';        // 绋冲畾鐗堟湰
const version = '2.1.0-beta';   // 娴嬭瘯鐗堟湰
```

### 7. 鎻愪緵娓呮櫚鐨勬枃妗?
鍖呭惈瑙ｉ噴澶嶆潅閫昏緫鐨勬敞閲婏細
```javascript
// 妫€鏌ュ畯鏄惁鑷冲皯鏈?10 涓搷浣滐紝浠ラ伩鍏嶈繍琛屽井灏忕殑瀹?
if (event.getMacroData().length < 10) {
    mm.log('瀹忓お鐭紝璺宠繃');
    return;
}
```

### 8. 杩涜褰诲簳鐨勬祴璇?
- 浣跨敤涓嶅悓鐨勯厤缃繘琛屾祴璇?
- 浣跨敤缂哄皯鍙€変緷璧栫殑鏂瑰紡娴嬭瘯
- 娴嬭瘯閿欒鍦烘櫙
- 浣跨敤鍚勭浜嬩欢缁勫悎杩涜娴嬭瘯

## 绀轰緥

### 绀轰緥 1锛氭搷浣滆鏁板櫒鑴氭湰

璁℃暟瀹忎腑鎿嶄綔鐨勭畝鍗曡剼鏈細

```javascript
const registry_name = 'action_counter';
const display_name = '鎿嶄綔璁℃暟鍣?;
const version = '1.0.0';
const author = '寮€鍙戣€?;
const description = '璁℃暟骞惰褰曞畯鎿嶄綔';
const available_version = '1.0.0';

var totalActions = 0;
var totalPlaybacks = 0;

mm.on('io.github.samera2022.samacros.api.event.events.AfterRecordStopEvent', (event) => {
    totalActions = event.getActionsCount();
    mm.log('褰曞埗浜?' + totalActions + ' 涓搷浣?);
});

mm.on('io.github.samera2022.samacros.api.event.events.OnLoopCompleteEvent', (event) => {
    totalPlaybacks++;
    mm.log('瀹屾垚鎾斁 ' + totalPlaybacks);
});

mm.on('io.github.samera2022.samacros.api.event.events.OnPlaybackAbortedEvent', (event) => {
    mm.log('鍦?' + totalPlaybacks + ' 涓惊鐜悗涓鎾斁');
});
```

### 绀轰緥 2锛氶€氱煡鑴氭湰

涓洪噸瑕佷簨浠舵樉绀洪€氱煡锛?

```javascript
const registry_name = 'notification_system';
const display_name = '閫氱煡绯荤粺';
const version = '1.0.0';
const author = '寮€鍙戣€?;
const description = '涓哄畯浜嬩欢鏄剧ず閫氱煡';
const available_version = '1.0.0';

const context = mm.getContext();

mm.on('io.github.samera2022.samacros.api.event.events.BeforePlaybackStartEvent', (event) => {
    context.showToast('鎾斁宸插紑濮?, '閲嶅 ' + event.getRepeatCount() + ' 娆?);
});

mm.on('io.github.samera2022.samacros.api.event.events.OnPlaybackAbortedEvent', (event) => {
    context.showToast('鎾斁宸蹭腑姝?, '瀹忔墽琛屽凡鍋滄');
});

mm.on('io.github.samera2022.samacros.api.event.events.OnLoopCompleteEvent', (event) => {
    var progress = Math.round((event.getLoopNumber() / event.getTotalLoops()) * 100);
    if (progress % 25 === 0) { // 姣?25% 鏄剧ず涓€娆?
        context.showToast('杩涘害', progress + '% 瀹屾垚');
    }
});
```

### 绀轰緥 3锛氳緭鍏ョ瓫閫夎剼鏈?

鍦ㄥ綍鍒舵湡闂寸瓫閫夋煇浜涜緭鍏ワ細

```javascript
const registry_name = 'input_filter';
const display_name = '杈撳叆绛涢€夊櫒';
const version = '1.0.0';
const author = '寮€鍙戣€?;
const description = '绛涢€夐紶鏍囩Щ鍔ㄤ簨浠?;
const available_version = '1.0.0';

// 杈撳叆绫诲瀷甯告暟
const MOUSE_MOVE = 0;
const MOUSE_PRESS = 1;
const MOUSE_RELEASE = 2;
const MOUSE_WHEEL = 3;
const KEY_PRESS = 10;
const KEY_RELEASE = 11;

mm.on('io.github.samera2022.samacros.api.event.events.OnInputCapturedEvent', (event) => {
    // 璺宠繃褰曞埗榧犳爣绉诲姩浠ュ噺灏戝櫔澹?
    if (event.getInputType() === MOUSE_MOVE) {
        event.setCancelled(true);
        mm.log('鍦?(' + event.getX() + ', ' + event.getY() + ') 澶勭瓫閫夊嚭榧犳爣绉诲姩');
    }
});
```

### 绀轰緥 4锛氭櫤鑳藉畯鎵ц鑴氭湰

甯︽湁楠岃瘉鐨勯珮绾у畯鎵ц锛?

```javascript
const registry_name = 'smart_executor';
const display_name = '鏅鸿兘瀹忔墽琛屽櫒';
const version = '1.0.0';
const author = '寮€鍙戣€?;
const description = '鏅鸿兘楠岃瘉鍜屾墽琛屽畯';
const available_version = '1.0.0';

var executionLog = [];

mm.on('io.github.samera2022.samacros.api.event.events.BeforePlaybackStartEvent', (event) => {
    var actions = event.getMacroData();
    
    if (actions.length === 0) {
        mm.log('閿欒锛氭病鏈夋搷浣滃彲鎾斁');
        event.setCancelled(true);
        return;
    }
    
    if (event.getRepeatCount() > 100) {
        mm.log('璀﹀憡锛氶噸澶嶆鏁板緢楂橈紙' + event.getRepeatCount() + '锛?);
    }
    
    executionLog = [];
    mm.log('寮€濮嬫挱鏀撅紝鍏?' + actions.length + ' 涓搷浣?);
});

mm.on('io.github.samera2022.samacros.api.event.events.BeforeStepExecuteEvent', (event) => {
    var action = event.getAction();
    executionLog.push({
        index: event.getActionIndex(),
        timestamp: new Date().getTime()
    });
});

mm.on('io.github.samera2022.samacros.api.event.events.OnLoopCompleteEvent', (event) => {
    mm.log('寰幆 ' + event.getLoopNumber() + '/' + event.getTotalLoops() + ' 宸插畬鎴?);
});

mm.on('io.github.samera2022.samacros.api.event.events.OnPlaybackAbortedEvent', (event) => {
    mm.log('鍦ㄦ墽琛?' + executionLog.length + ' 涓搷浣滃悗涓鎾斁');
});
```

## 鏁呴殰鎺掗櫎

### 鑴氭湰涓嶅姞杞?
- 妫€鏌ュ厓鏁版嵁鏍煎紡锛堟墍鏈夊繀闇€瀛楁閮藉瓨鍦級
- 楠岃瘉鏂囦欢浠?`.js` 缁撳熬
- 妫€鏌ユ帶鍒跺彴鏄惁鏈夎В鏋愰敊璇?

### 浜嬩欢涓嶈Е鍙?
- 楠岃瘉浜嬩欢绫诲悕鏄惁姝ｇ‘
- 妫€鏌ヨ剼鏈槸鍚﹀湪 UI 涓惎鐢?
- 瀹℃煡鍥炶皟鍑芥暟璇硶

### 鍘熺敓璁块棶闂
- 纭繚 `requires_native_access` 璁剧疆涓?`true`
- 妫€鏌ヤ綔鑰呮垨鑴氭湰鏄惁鍦ㄧ櫧鍚嶅崟涓?
- 鍦ㄨ闂?Java API 鏃朵娇鐢?try-catch 鍧?

### 渚濊禆闂
- 楠岃瘉渚濊禆 `registry_name` 瀹屽叏鍖归厤
- 妫€鏌ユ槸鍚﹀瓨鍦ㄥ惊鐜緷璧?
- 纭繚纭緷璧栧凡瀹夎骞跺惎鐢?

## 鑾峰彇甯姪

- 鏌ラ槄 saMacros 鏂囨。
- 鏌ョ湅鑴氭湰鐩綍涓殑绀轰緥鑴氭湰
- 妫€鏌ユ帶鍒跺彴杈撳嚭浠ヨ幏鍙栬缁嗙殑閿欒娑堟伅
- 浣跨敤娓呮櫚鐨勯敊璇弿杩版姤鍛婇棶棰?

---

**鏈€鍚庢洿鏂帮細** 2026 骞?2 鏈? 
**saMacros 鐗堟湰锛?* 2.0.0+


