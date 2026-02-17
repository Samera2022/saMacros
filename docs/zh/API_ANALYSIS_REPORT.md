# saMacros API 鍒嗘瀽鎬荤粨鎶ュ憡

## 姒傝堪

閫氳繃璇︾粏鍒嗘瀽 saMacros app 妯″潡鐨勬簮浠ｇ爜锛屾垜浠彂鐜颁簡澶ч噺鍙互鍚戣剼鏈紑鍙戣€呭紑鏀剧殑瀹炵敤 API銆傛湰鎶ュ憡鎬荤粨浜嗙幇鏈?API銆佸凡瀹炵幇浣嗘湭寮€鏀剧殑 API锛屼互鍙婃帹鑽愮殑鏈潵 API銆?

---

## 涓€銆佸凡鍒嗘瀽鐨勬ā鍧楃粨鏋?

### 搴旂敤妯″潡鏋舵瀯

```
samacros-app/src/main/java/io/github/samera2022/samacros/app/
鈹溾攢鈹€ manager/                    # 涓氬姟閫昏緫绠＄悊鍣?
鈹?  鈹溾攢鈹€ MacroManager           # 瀹忔搷浣滃拰鎾斁鎺у埗 鉁?閮ㄥ垎宸插紑鏀?
鈹?  鈹溾攢鈹€ LogManager             # 鏃ュ織绠＄悊
鈹?  鈹斺攢鈹€ CacheManager           # 缂撳瓨绠＄悊
鈹溾攢鈹€ script/                     # 鑴氭湰绠＄悊
鈹?  鈹溾攢鈹€ ScriptAPI              # 鉁?宸插紑鏀剧粰鑴氭湰
鈹?  鈹溾攢鈹€ ScriptManager          # 鑴氭湰鐢熷懡鍛ㄦ湡绠＄悊
鈹?  鈹溾攢鈹€ ScriptContext          # 鉁?閮ㄥ垎宸插紑鏀?
鈹?  鈹溾攢鈹€ ScriptDescription      # 鑴氭湰鍏冩暟鎹?
鈹?  鈹斺攢鈹€ ScriptPlugin           # 鑴氭湰鎻掍欢灏佽
鈹溾攢鈹€ util/                       # 宸ュ叿绫?
鈹?  鈹溾攢鈹€ ScreenUtil             # 灞忓箷鍧愭爣鍜岀缉鏀?鈿?鍙互寮€鏀?
鈹?  鈹溾攢鈹€ SystemUtil             # 绯荤粺淇℃伅鑾峰彇 鈿?鍙互寮€鏀?
鈹?  鈹溾攢鈹€ OtherUtil              # 鍏朵粬宸ュ叿
鈹?  鈹溾攢鈹€ FileUtil               # 鏂囦欢鎿嶄綔
鈹?  鈹斺攢鈹€ ComponentUtil          # UI 缁勪欢宸ュ叿
鈹溾攢鈹€ config/                     # 閰嶇疆绠＄悊
鈹?  鈹溾攢鈹€ ConfigManager          # 閰嶇疆璇诲彇
鈹?  鈹斺攢鈹€ WhitelistManager       # 鏉冮檺鐧藉悕鍗?
鈹斺攢鈹€ constant/                   # 甯搁噺瀹氫箟
```

---

## 浜屻€佺幇鏈?API 鎬荤粨

### 2.1 宸插紑鏀剧殑 API锛堥€氳繃 `mm` 瀵硅薄锛?

#### 鑴氭湰 API (`IScriptAPI`)

**鍙敤鏂规硶锛?*

| 鏂规硶 | 绛惧悕 | 鐢ㄩ€?|
|------|------|------|
| `on()` | `on(String eventClassName, Consumer<Event> callback)` | 娉ㄥ唽浜嬩欢鐩戝惉鍣?|
| `getContext()` | `getContext(): IScriptContext` | 鑾峰彇鑴氭湰涓婁笅鏂?|
| `log()` | `log(String message)` | 杈撳嚭鏃ュ織 |
| `cleanup()` | `cleanup()` | 娓呯悊璧勬簮锛堣嚜鍔ㄨ皟鐢級 |

#### 鑴氭湰涓婁笅鏂?API (`IScriptContext`)

**鍙敤鏂规硶锛?*

| 鏂规硶 | 绛惧悕 | 鐢ㄩ€?|
|------|------|------|
| `simulate()` | `simulate(IMouseAction action)` | 妯℃嫙榧犳爣/閿洏鎿嶄綔 - **鉁?宸插疄鐜?* |
| `getPixelColor()` | `getPixelColor(int x, int y): Color` | 鑾峰彇灞忓箷鍍忕礌棰滆壊 - **鉁?宸插疄鐜?* |
| `showToast()` | `showToast(String title, String msg)` | 鏄剧ず閫氱煡 - **鉁?宸插疄鐜?* |
| `getAppConfig()` | `getAppConfig(): IConfig` | 鑾峰彇搴旂敤閰嶇疆 |

**瀹炵幇缁嗚妭锛?*
- `simulate()`: 璋冪敤 `action.perform()`锛屽寘鍚┖鍊兼鏌ュ拰寮傚父澶勭悊
- `getPixelColor()`: 浣跨敤 `java.awt.Robot.getPixelColor()` 鎹曡幏灞忓箷鍍忕礌
- `showToast()`: 浣跨敤 SystemTray 鍜?TrayIcon 鏄剧ず閫氱煡锛屽涓嶆敮鎸佸垯鍥為€€鍒版帶鍒跺彴杈撳嚭

#### 搴旂敤閰嶇疆 API (`IConfig`)

**鍙敤鏂规硶锛?*

| 鏂规硶 | 绛惧悕 | 鐢ㄩ€?|
|------|------|------|
| `getBoolean()` | `getBoolean(String key): boolean` | 璇诲彇甯冨皵閰嶇疆 |
| `getInt()` | `getInt(String key): int` | 璇诲彇鏁存暟閰嶇疆 |
| `getDouble()` | `getDouble(String key): double` | 璇诲彇娴偣鏁伴厤缃?|
| `getString()` | `getString(String key): String` | 璇诲彇瀛楃涓查厤缃?|
| `getKeyMap()` | `getKeyMap(): Map<String, String>` | 鑾峰彇鎵€鏈夐厤缃?|

#### 绯荤粺淇℃伅 API (`ISystemInfo`) - **v2.1 鏂板**

**鍙敤鏂规硶锛?*

| 鏂规硶 | 绛惧悕 | 鐢ㄩ€?|
|------|------|------|
| `getScale()` | `getScale(): double[]` | 鑾峰彇 DPI 缂╂斁姣斾緥 [scaleX, scaleY] |
| `isSystemDarkMode()` | `isSystemDarkMode(): boolean` | 妫€鏌ョ郴缁熸槸鍚︿负娣辫壊妯″紡 |
| `getSystemLanguage()` | `getSystemLanguage(): String` | 鑾峰彇绯荤粺璇█浠ｇ爜 |
| `getOSName()` | `getOSName(): String` | 鑾峰彇鎿嶄綔绯荤粺鍚嶇О |
| `getJavaVersion()` | `getJavaVersion(): String` | 鑾峰彇 Java 鐗堟湰 |

#### 灞忓箷淇℃伅 API (`IScreenInfo`) - **v2.1 鏂板**

**鍙敤鏂规硶锛?*

| 鏂规硶 | 绛惧悕 | 鐢ㄩ€?|
|------|------|------|
| `getWidth()` | `getWidth(): int` | 鑾峰彇涓诲睆骞曞搴?|
| `getHeight()` | `getHeight(): int` | 鑾峰彇涓诲睆骞曢珮搴?|
| `getScreenCount()` | `getScreenCount(): int` | 鑾峰彇灞忓箷/鏄剧ず鍣ㄦ暟閲?|
| `getVirtualOrigin()` | `getVirtualOrigin(): Point` | 鑾峰彇铏氭嫙灞忓箷鍘熺偣 |
| `normalizeToVirtualOrigin()` | `normalizeToVirtualOrigin(int x, int y): Point` | 鍧愭爣褰掍竴鍖?|
| `denormalizeFromVirtualOrigin()` | `denormalizeFromVirtualOrigin(int x, int y): Point` | 鍧愭爣鍙嶅綊涓€鍖?|

#### 瀹忎俊鎭?API (`IMacroInfo`) - **v2.1 鏂板**

**鍙敤鏂规硶锛?*

| 鏂规硶 | 绛惧悕 | 鐢ㄩ€?|
|------|------|------|
| `isRecording()` | `isRecording(): boolean` | 妫€鏌ユ槸鍚︽鍦ㄥ綍鍒?|
| `isPlaying()` | `isPlaying(): boolean` | 妫€鏌ユ槸鍚︽鍦ㄦ挱鏀?|
| `isPaused()` | `isPaused(): boolean` | 妫€鏌ユ挱鏀炬槸鍚︽殏鍋?|
| `getActionsCount()` | `getActionsCount(): int` | 鑾峰彇瀹忎腑鐨勫姩浣滄暟閲?|

#### 鍥介檯鍖?API (`II18n`) - **v2.1 鏂板**

**鍙敤鏂规硶锛?*

| 鏂规硶 | 绛惧悕 | 鐢ㄩ€?|
|------|------|------|
| `get()` | `get(String key): String` | 鑾峰彇缈昏瘧鏂囨湰 |
| `hasKey()` | `hasKey(String key): boolean` | 妫€鏌ョ炕璇戦敭鏄惁瀛樺湪 |
| `getCurrentLanguage()` | `getCurrentLanguage(): String` | 鑾峰彇褰撳墠璇█浠ｇ爜 |

#### 榧犳爣淇℃伅 API (`IMouseInfo`)

**鍙敤鏂规硶锛?*

| 鏂规硶 | 绛惧悕 | 鐢ㄩ€?|
|------|------|------|
| `getPosition()` | `getPosition(): Point` | 鑾峰彇褰撳墠榧犳爣鍏夋爣浣嶇疆 |

#### 浜嬩欢绯荤粺 (20+ 浜嬩欢)

宸插畬鍏ㄨ褰曞湪涓诲紑鍙戞寚鍗椾腑锛屽寘鎷細
- 搴旂敤鐢熷懡鍛ㄦ湡浜嬩欢
- 褰曞埗浜嬩欢
- 鍥炴斁浜嬩欢
- 鏂囦欢鎿嶄綔浜嬩欢
- 閰嶇疆鍙樺寲浜嬩欢

---

## 涓夈€佸凡瀹炵幇浣嗘湭鍏呭垎寮€鏀剧殑 API

### 3.1 MacroManager - 瀹忕鐞嗗櫒

**褰撳墠瀹炵幇锛?*

```java
// 鐘舵€佹煡璇紙鍙闂級
public static boolean isRecording();          // 鏄惁姝ｅ湪褰曞埗
public static boolean isPlaying();        // 鏄惁姝ｅ湪鎾斁
public static boolean isPaused();         // 鏄惁宸叉殏鍋?

// 瀹忔帶鍒讹紙鍙闂級
public static void startRecording();      // 寮€濮嬪綍鍒?
public static void stopRecording();       // 鍋滄褰曞埗
public static void play();                // 鎾斁
public static void pause();               // 鏆傚仠
public static void resume();              // 鎭㈠
public static void abort();               // 涓

// 鏁版嵁璁块棶锛堥儴鍒嗗彲璁块棶锛?
public static List<MouseAction> getActions();     // 鑾峰彇鎿嶄綔鍒楄〃
public static long getLastTime();                 // 鑾峰彇涓婃鎿嶄綔鏃堕棿
public static void recordAction();                // 璁板綍鎿嶄綔

// 鏂囦欢鎿嶄綔锛圲I 缁戝畾锛?
public static void saveToFile();          // 淇濆瓨鍒版枃浠?
public static void loadFromFile();        // 浠庢枃浠跺姞杞?
```

**寤鸿锛?* 涓鸿剼鏈紑鏀?`mm.macro` 瀵硅薄锛屾彁渚涗互涓嬪寮哄姛鑳斤細

```javascript
mm.macro.isRecording()        // 鉁?宸插彲閫氳繃浜嬩欢妫€娴?
mm.macro.isPlaying()          // 鉁?宸插彲閫氳繃浜嬩欢妫€娴?
mm.macro.isPaused()           // 鉁?宸插彲閫氳繃浜嬩欢妫€娴?
mm.macro.getActions()         // 鉁?鍙€氳繃浜嬩欢鑾峰彇
mm.macro.getActionsCount()    // 鎺ㄨ崘娣诲姞
mm.macro.getCurrentLoop()     // 鎺ㄨ崘娣诲姞
mm.macro.getCurrentActionIndex() // 鎺ㄨ崘娣诲姞
mm.macro.getLastSaveDirectory()  // 鎺ㄨ崘娣诲姞
```

### 3.2 ScreenUtil - 灞忓箷宸ュ叿绫?

**褰撳墠瀹炵幇锛?*

```java
// 澶氬睆骞曟敮鎸佸拰 DPI 缂╂斁澶勭悊
public static Point denormalizeFromVirtualOrigin(int x, int y);
public static Point normalizeToVirtualOrigin(int x, int y);
private static Point getVirtualOrigin();
```

**寤鸿锛?* 閫氳繃 `mm.system` 瀵硅薄寮€鏀?

```javascript
mm.system.getScale()          // 鑾峰彇 DPI 缂╂斁鍥犲瓙
mm.system.getVirtualOrigin()  // 鑾峰彇铏氭嫙灞忓箷鍘熺偣
mm.system.normalizeToVirtualOrigin(x, y)    // 鍧愭爣杞崲
mm.system.denormalizeFromVirtualOrigin(x, y) // 鍧愭爣杞崲
```

**瀹為檯搴旂敤锛?* 澶氬睆骞曞拰楂?DPI 鐜涓嬬殑鍧愭爣澶勭悊

### 3.3 SystemUtil - 绯荤粺宸ュ叿绫?

**褰撳墠瀹炵幇锛?*

```java
// 鑾峰彇绯荤粺 DPI 缂╂斁
public static double[] getScale();

// 鑾峰彇绯荤粺璇█
public static String getSystemLang(String[] availableLangs);

// 妫€鏌ユ繁鑹叉ā寮忥紙浠?Windows 10+锛?
public static boolean isSystemDarkMode();
```

**寤鸿锛?* 閫氳繃 `mm.system` 瀵硅薄寮€鏀?

```javascript
mm.system.getScale()          // 鑾峰彇缂╂斁鍥犲瓙
mm.system.getSystemLanguage() // 鑾峰彇绯荤粺璇█
mm.system.isSystemDarkMode()  // 鏄惁娣辫壊妯″紡
mm.system.getOSName()         // 鑾峰彇鎿嶄綔绯荤粺
mm.system.getJavaVersion()    // 鑾峰彇 Java 鐗堟湰
```

### 3.4 Localizer - 鍥介檯鍖栨敮鎸?

**褰撳墠瀹炵幇锛?*

```java
// 鍔犺浇璇█鏂囦欢鍜岃幏鍙栫炕璇?
public static void load(String lang);
public static String get(String key);
public static boolean hasKey(String key);
private static Map<String, String> loadLanguageMap(String lang);
```

**寤鸿锛?* 閫氳繃 `mm.i18n` 瀵硅薄寮€鏀?

```javascript
mm.i18n.get(key)              // 鑾峰彇缈昏瘧瀛楃涓?
mm.i18n.hasKey(key)           // 妫€鏌ラ敭鏄惁瀛樺湪
mm.i18n.getCurrentLanguage()  // 鑾峰彇褰撳墠璇█
mm.i18n.getAvailableLanguages() // 鑾峰彇鍙敤璇█
mm.i18n.switchLanguage(lang)  // 鍒囨崲璇█锛堟帹鑽愶級
```

---

## 鍥涖€佹帹鑽愮殑鏂?API锛堜紭鍏堢骇鎺掑垪锛?

### 浼樺厛绾?1锛堥珮锛? v2.1.0

#### 1. Macro Management API
```javascript
mm.macro.getActionsCount()        // 鑾峰彇鎿嶄綔鏁伴噺
mm.macro.getCurrentLoop()         // 褰撳墠寰幆鍙?
mm.macro.getCurrentActionIndex()  // 褰撳墠鎿嶄綔绱㈠紩
mm.macro.getLastSaveDirectory()   // 涓婃淇濆瓨鐩綍
```

**鐢ㄩ€旓細** 
- 鑴氭湰闇€瑕佺煡閬撳畯鐨勮缁嗘墽琛岀姸鎬?
- 杩涘害鐩戞帶鍜屾潯浠舵墽琛?

#### 2. System Information API
```javascript
mm.system.getScale()              // DPI 缂╂斁
mm.system.isSystemDarkMode()      // 娣辫壊妯″紡
mm.system.getSystemLanguage()     // 绯荤粺璇█
mm.system.getOSName()             // 鎿嶄綔绯荤粺
mm.system.getJavaVersion()        // Java 鐗堟湰
```

**鐢ㄩ€旓細**
- 鏍规嵁绯荤粺閰嶇疆璋冩暣瀹忚涓?
- 澶勭悊澶氬睆骞曞拰楂?DPI 鐜
- 骞冲彴鐗瑰畾浼樺寲

### 浼樺厛绾?2锛堜腑锛? v2.2.0

#### 3. Internationalization API
```javascript
mm.i18n.get(key)                  // 鑾峰彇缈昏瘧
mm.i18n.getCurrentLanguage()      // 褰撳墠璇█
mm.i18n.getAvailableLanguages()   // 鍙敤璇█鍒楄〃
```

**鐢ㄩ€旓細**
- 澶氳瑷€鑴氭湰寮€鍙?
- 鏈湴鍖栨棩蹇楀拰閫氱煡

#### 4. Clipboard API
```javascript
mm.clipboard.getText()            // 璇诲彇鏂囨湰
mm.clipboard.setText(text)        // 璁剧疆鏂囨湰
mm.clipboard.getFiles()           // 璇诲彇鏂囦欢鍒楄〃
```

**鐢ㄩ€旓細**
- 涓庡叾浠栧簲鐢ㄩ泦鎴?
- 鑷姩澶嶅埗/绮樿创宸ヤ綔娴?

#### 5. File API
```javascript
mm.file.readText(path)            // 璇诲彇鏂囨湰鏂囦欢
mm.file.writeText(path, content)  // 鍐欏叆鏂囨湰鏂囦欢
mm.file.exists(path)              // 妫€鏌ユ枃浠舵槸鍚﹀瓨鍦?
mm.file.listDirectory(path)       // 鍒楀嚭鐩綍鍐呭
```

**鐢ㄩ€旓細**
- 浠庨厤缃枃浠惰鍙栧弬鏁?
- 杈撳嚭鎵ц缁撴灉鍜屾棩蹇?
- 鑴氭湰闂寸殑鏁版嵁鍏变韩

### 浼樺厛绾?3锛堜綆锛? v2.3.0+

#### 6. Window Management API
```javascript
mm.window.getActiveWindow()       // 鑾峰彇娲昏穬绐楀彛
mm.window.getAllWindows()         // 鑾峰彇鎵€鏈夌獥鍙?
mm.window.focusWindow(title)      // 鐒︾偣鏌愪釜绐楀彛
```

**鐢ㄩ€旓細**
- 閽堝鐗瑰畾搴旂敤鐨勮嚜鍔ㄥ寲
- 绐楀彛鐘舵€佹娴?

#### 7. Network API
```javascript
mm.http.get(url)                  // GET 璇锋眰
mm.http.post(url, data)           // POST 璇锋眰
mm.http.download(url, path)       // 涓嬭浇鏂囦欢
```

**鐢ㄩ€旓細**
- 涓庡湪绾挎湇鍔￠泦鎴?
- 鏁版嵁涓婁紶鍜屽悓姝?

#### 8. Timer API
```javascript
mm.timer.setTimeout(fn, delay)    // 寤惰繜鎵ц
mm.timer.setInterval(fn, delay)   // 鍛ㄦ湡鎵ц
mm.timer.delay(ms)                // 寤惰繜 Promise
```

**鐢ㄩ€旓細**
- 寮傛鎿嶄綔鎺у埗
- 瀹氭椂浠诲姟

---

## 浜斻€丄PI 璁捐鎸囧鍘熷垯

### 5.1 瀹夊叏鎬ц€冭檻

| API 绫诲瀷 | 瀹夊叏绾у埆 | 璇存槑 |
|---------|---------|------|
| 鍙閰嶇疆 | 楂?| 宸插疄鐜帮紝瀹夊叏 |
| 浜嬩欢鐩戝惉 | 楂?| 宸插疄鐜帮紝瀹夊叏 |
| 鏂囦欢鎿嶄綔 | 涓?| 闇€瑕佹潈闄愭帶鍒?|
| 缃戠粶鎿嶄綔 | 浣?| 闇€瑕佹槑纭鍙?|
| 绯荤粺鎿嶄綔 | 浣?| 闇€瑕佸師鐢熻闂壒鍑?|

### 5.2 瀹炵幇妯″紡

**寤鸿鐨勫璞＄粨鏋勶細**

```javascript
// 鏍稿績瀵硅薄
mm.on()           // 浜嬩欢鐩戝惉锛堢幇鏈夛級
mm.log()          // 鏃ュ織杈撳嚭锛堢幇鏈夛級
mm.getContext()   // 鑾峰彇涓婁笅鏂囷紙鐜版湁锛?

// 鎵╁睍瀵硅薄锛堟帹鑽愶級
mm.macro          // 瀹忕鐞?
mm.system         // 绯荤粺淇℃伅
mm.i18n           // 鍥介檯鍖?
mm.clipboard      // 鍓创鏉匡紙闇€鏉冮檺锛?
mm.file           // 鏂囦欢鎿嶄綔锛堥渶鏉冮檺锛?
mm.window         // 绐楀彛绠＄悊锛堥渶鏉冮檺锛?
mm.http           // 缃戠粶锛堥渶鏉冮檺锛?
mm.timer          // 瀹氭椂鍣?
mm.perf           // 鎬ц兘鐩戞帶
```

### 5.3 閿欒澶勭悊

**鎺ㄨ崘鐨勯敊璇鐞嗘ā寮忥細**

```javascript
// 1. 鐗规€ф娴?
if (typeof mm.macro !== 'undefined') {
    // 浣跨敤鏂?API
}

// 2. Try-Catch
try {
    const scale = mm.system.getScale();
} catch (error) {
    mm.log('Error: ' + error.message);
}

// 3. 鍥為€€鏈哄埗
try {
    return mm.macro.getActionsCount();
} catch (e) {
    // 浣跨敤浜嬩欢鏇夸唬
}
```

---

## 鍏€佸疄鐜版垚鏈瘎浼?

| API 妯″潡 | 瀹炵幇闅惧害 | 浠ｇ爜琛屾暟 | 棰勮宸ユ椂 |
|---------|---------|---------|---------|
| `mm.macro` | 浣?| 200-300 | 2-4 灏忔椂 |
| `mm.system` | 浣?| 100-150 | 1-2 灏忔椂 |
| `mm.i18n` | 浣?| 50-100 | 1 灏忔椂 |
| `mm.clipboard` | 涓?| 150-250 | 3-5 灏忔椂 |
| `mm.file` | 涓?| 200-300 | 4-6 灏忔椂 |
| `mm.window` | 楂?| 300-500 | 6-10 灏忔椂 |
| `mm.http` | 涓?| 150-250 | 3-5 灏忔椂 |
| `mm.timer` | 浣?| 100-150 | 1-2 灏忔椂 |

**鎬昏锛堝叏閮級锛?* 绾?1100-2000 琛屼唬鐮侊紝20-35 灏忔椂宸ユ椂

---

## 涓冦€佸畨鍏ㄥ拰闅愮鑰冭檻

### 7.1 鏉冮檺妯″瀷

```
鈹屸攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹?
鈹?   搴旂敤绾?API锛堟棤闇€鏉冮檺锛?        鈹?
鈹? 鈥?浜嬩欢鐩戝惉                       鈹?
鈹? 鈥?瀹忕姸鎬佹煡璇?                    鈹?
鈹? 鈥?鏃ュ織杈撳嚭                       鈹?
鈹斺攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹?
        鈫?
鈹屸攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹?
鈹?   楂樻潈闄?API锛堥渶鏄庣‘璁稿彲锛?      鈹?
鈹? 鈥?鏂囦欢鎿嶄綔                       鈹?
鈹? 鈥?缃戠粶鎿嶄綔                       鈹?
鈹? 鈥?鍓创鏉胯闂?                    鈹?
鈹? 鈥?绐楀彛鎿嶄綔                       鈹?
鈹斺攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹?
        鈫?
鈹屸攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹?
鈹?   绯荤粺绾?API锛堥渶鍘熺敓璁块棶鎵瑰噯锛?  鈹?
鈹? 鈥?绯荤粺鍛戒护鎵ц                   鈹?
鈹? 鈥?娉ㄥ唽琛ㄤ慨鏀?                    鈹?
鈹? 鈥?杩涚▼鎿嶄綔                       鈹?
鈹斺攢鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹?
```

### 7.2 鏉冮檺妫€鏌?

**寤鸿鐨勬潈闄愭鏌ヤ唬鐮侊細**

```java
// 鍦?ScriptAPI 涓坊鍔犳潈闄愭鏌?
public class ScriptAPI implements IScriptAPI {
    private final ScriptDescription description;
    
    public void allowFileAccess(Consumer<FileAPI> callback) {
        if (description.isRequiresNativeAccess() || 
            WhitelistManager.isWhitelisted(description)) {
            callback.accept(new FileAPI());
        } else {
            throw new SecurityException("File access not permitted");
        }
    }
}
```

---

## 鍏€佷娇鐢ㄧず渚嬪拰鐢ㄤ緥

### 鐢ㄤ緥 1锛氳嚜閫傚簲瀹忔墽琛?

```javascript
// 鏍规嵁绯荤粺閰嶇疆鑷姩璋冩暣瀹?
mm.on('BeforePlaybackStartEvent', (event) => {
    const scale = mm.system.getScale();
    const isDark = mm.system.isSystemDarkMode();
    
    if (scale[0] > 1.5) {
        mm.log('High DPI detected');
    }
    if (isDark) {
        mm.log('Dark mode enabled');
    }
});
```

### 鐢ㄤ緥 2锛氬璇█鏃ュ織璁板綍

```javascript
// 浣跨敤绯荤粺璇█璁板綍鏃ュ織
mm.on('OnLoopCompleteEvent', (event) => {
    const lang = mm.i18n.getCurrentLanguage();
    const msg = mm.i18n.get('log.loop_complete');
    mm.log(msg + ' ' + event.getLoopNumber());
});
```

### 鐢ㄤ緥 3锛氳繘搴︾洃鎺?

```javascript
// 鐩戞帶鎵ц杩涘害
mm.on('BeforeStepExecuteEvent', (event) => {
    const total = mm.macro.getActionsCount();
    const current = mm.macro.getCurrentActionIndex();
    const progress = Math.round((current / total) * 100);
    
    if (progress % 25 === 0) {
        mm.log('Progress: ' + progress + '%');
    }
});
```

---

## 涔濄€佸缓璁拰缁撹

### 涓昏寤鸿

1. **绔嬪嵆瀹炵幇锛坴2.1.0锛?*
   - `mm.macro` - 瀹忕姸鎬佸拰鎺у埗鎺ュ彛
   - `mm.system` - 绯荤粺淇℃伅鎺ュ彛
   - 浼樺厛绾ч珮锛岄闄╀綆锛屾敹鐩婂ぇ

2. **璁″垝瀹炵幇锛坴2.2.0锛?*
   - `mm.i18n` - 鍥介檯鍖栨敮鎸?
   - `mm.clipboard` - 鍓创鏉胯闂?
   - `mm.file` - 鏂囦欢鎿嶄綔锛堝彈闄愬埗锛?

3. **鏈潵鑰冭檻锛坴2.3.0+锛?*
   - `mm.window` - 绐楀彛绠＄悊
   - `mm.http` - 缃戠粶鎿嶄綔
   - 楂橀闄╋紝闇€鍏呭垎鐨勫畨鍏ㄨ璁?

### 鍏抽敭瀹夊叏寤鸿

1. **鏉冮檺鐧藉悕鍗?*
   - 缁存姢宸叉壒鍑嗙殑鑴氭湰/浣滆€呭垪琛?
   - 瀹氭湡瀹¤鏉冮檺浣跨敤

2. **娌欑闅旂**
   - 闄愬埗鏂囦欢绯荤粺璁块棶鑼冨洿
   - 闄愬埗缃戠粶璁块棶鍩熷悕

3. **瀹¤鏃ュ織**
   - 璁板綍鎵€鏈夋晱鎰熸搷浣?
   - 鎻愪緵鐢ㄦ埛鍙鐨勬潈闄愪娇鐢ㄦ姤鍛?

4. **鏂囨。璀﹀憡**
   - 娓呮鏍囨敞鏉冮檺瑕佹眰
   - 瑙ｉ噴娼滃湪瀹夊叏椋庨櫓

---

## 闄勫綍锛氬弬鑰冭祫婧?

- **婧愭枃浠朵綅缃?*
  - ScriptAPI: `samacros-app/src/main/java/.../script/ScriptAPI.java`
  - MacroManager: `samacros-app/src/main/java/.../manager/MacroManager.java`
  - ScreenUtil: `samacros-app/src/main/java/.../util/ScreenUtil.java`
  - SystemUtil: `samacros-app/src/main/java/.../util/SystemUtil.java`
  - Localizer: `samacros-app/src/main/java/.../Localizer.java`

- **鐩稿叧鏂囨。**
  - SCRIPT_DEVELOPMENT_GUIDE.md - 涓诲紑鍙戞寚鍗?
  - EXTENDED_API_REFERENCE.md - 鎵╁睍 API 鍙傝€?

---

**鎶ュ憡瀹屾垚鏃ユ湡锛?* 2026 骞?2 鏈?12 鏃? 
**鍒嗘瀽鑼冨洿锛?* saMacros v2.0.0  
**鍒嗘瀽娣卞害锛?* 婧愪唬鐮佺骇鍒? 
**鏂囨。鐗堟湰锛?* 1.0


