[![](https://jitpack.io/v/arksjs/NpUse-Android.svg)](https://jitpack.io/#arksjs/NpUse-Android)
# NP Android 接入文档

## 安装 SDK

### 1. 根 `build.gradle` 文件配置仓库

```gradle
repositories {
  # ...
  maven { url 'https://jitpack.io' }
}
```

### 2. 需要依赖的 module 的 `build.gradle` 添加依赖

```gradle
implementation 'com.github.arksjs:NpUse:v1.2.2'
```

## 集成

### 1. 在 `AndroidManifest.xml` 添加网络权限

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

#### 在 `Android12` 以上添加定时权限

```xml
<uses-permission android:name="android.permission.SCHEDULE_EXACT_ALARM" />
```

### 2. 初始化 SDK

#### 2.1 单ak上报

```
public static void initSdk(Application app, String appKey)
```

如：

```
GreeNp.initSdk(Application.this, "APP_KEY");
```

#### 2.2 多ak上报

```
public static void initSdk(Application application, String appKey, ArrayList<String> appKeyArray, ArrayList<String> eventMultiArray)
```

如：

```
ArrayList<String> appKeyArr = new ArrayList<>();
ArrayList<String> eventArr = new ArrayList<>();
GreeNp.initSdk(Application.this, "APP_KEY", appKeyArr, eventArr);
```

### 3. 查看日志输出

可以通过查询 tag=GreeNp 来获取 SDK 的打印日志

## 高级功能

1. 自定义事件统计

自定义事件需要在后台进行配置，具体可以查看产品说明书。

| 参数  | 类型              | 必需 | 默认值 | 描述                                                                                         |
| ----- | ----------------- | ---- | ------ | -------------------------------------------------------------------------------------------- |
| key   | String            | 是   |        | 描述用户的动作名称，不超过 255 个字符，支持特殊字符                                          |
| value | String/JSONObject | 否   |        | 当值为 JSONObject 类型时，每个 key 长度不能超过 255 个字符，其携带 key 的个数不能超过 100 个 |

使用方式：

```
JSONObject json = new JSONObject();
try {
    json.put("id", 3);
    json.put("name", "tom");
} catch (Exception e) {
    e.printStackTrace();
}

// 上报事件
GreeNp.trackEvent("event_name", json);  // 属性为 JSONObject
GreeNp.trackEvent("event_name", "1");   // 属性为 stirng
GreeNp.trackEvent("event_name");        // 无属性
```

2. 搜索词统计

获取系统或网站的访客搜索关键词数据。

```
GreeNp.trackSearch(searchWord)
```

| 参数       | 类型   | 必需 | 默认值 | 描述                                    |
| ---------- | ------ | ---- | ------ | --------------------------------------- |
| searchWord | String | 是   |        | 搜索词，不超过 255 个字符，支持特殊字符 |

使用方式：

```
GreeNp.trackSearch('搜索词')
```

3. 设置系统用户ID

```
GreeNp.setUID(uid)
```

| 参数       |   类型   | 必需 | 默认值 | 描述                                    |
| ---------  | ------- | ---- | ----- | --------------------------------------- |
| uid | String/int/long | 是 |       | 用户标识id，统计系统用户数，不超过 200 个字符 |

使用方式：

```
GreeNp.setUID('id')
GreeNp.clearUID() //清除id
```

4. 设置日志打印

```
GreeNp.setDebugLog(uid)
```

| 参数       |   类型   | 必需 | 默认值 | 描述                                    |
| ---------  | ------- | ---- | ------ | --------------------------------------- |
| isShow     | boolean | 是   |   true   | 是否打印日志 |

使用方式：

```
GreeNp.setDebugLog(true)
```