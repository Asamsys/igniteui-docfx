---
title: マップ | データ可視化ツール | Ignite UI for Angular | ジオグラフィック JSON データ | Infragistics
_description: マップは、ビューモデルの地理的位置や JSONファイルからロードされた地理的位置を含むデータを表示できます。詳細については、デモ、依存関係、使用方法、およびツールバーを参照してください。
_keywords: map, Ignite UI for Angular, infragistics
_language: ja
---

## 地理的位置と JSON ファイルのバインド

`IgxGeographicMap` は、さまざまな種類のファイルからロードされた地理データをプロットできます。たとえば、JavaScript Object Notation (JSON) ファイルから地理的位置をロードできます。

### デモ

<div class="sample-container" style="height: 400px">
    <iframe id="geo-map-binding-data-json-points-iframe" src='{environment:demosBaseUrl}/maps/geo-map-binding-data-json-points' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" disabled class="stackblitz-btn"   data-iframe-id="geo-map-binding-data-json-points-iframe" data-demos-base-url="{environment:demosBaseUrl}">StackBlitz で表示
    </button>
</div>

<div class="divider--half"></div>

### データ例

JSON ファイルからのデータの例:

```typescript
[
 { "n": "Sydney Island", "y": -16.68972, "x": 139.45917 },
 { "n": "Sydney Creek", "y": -16.3, "x": 128.95 },
 { "n": "Mount Sydney", "y": -21.39864, "x": 121.193 },
 ...
]
```

### コード スニペット

次のコードは、マップコンポーネント内の `GeographicHighDensityScatterSeries` を、ロードされた JSON ファイルから作成された地理的位置を含むオブジェクトの配列にバインドします。