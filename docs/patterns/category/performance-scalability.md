---
title: "パフォーマンスとスケーラビリティのパターン"
description: "パフォーマンスは、指定された期間内で任意のアクションを実行するシステムの応答性を示します。一方、スケーラビリティは、パフォーマンスに影響を与えずに負荷の増加に対応できる、またはすぐに追加できる使用可能なリソースに対するシステムの能力です。 通常、クラウド アプリケーションが直面するワークロードやアクティビティのピークは変動しています。 これらを予測することは、特にマルチテナント シナリオではほとんど不可能です。 代わりに、アプリケーションは、要求のピークに対応できるように制限範囲内でスケールアウトし、要求が減少するとスケールインできることが必要です。 スケーラビリティは、コンピューティング インスタンスだけではなく、データ ストレージやメッセージング インフラストラクチャなど、他の要素にとっても重要です。"
keywords: "設計パターン"
author: dragon119
ms.date: 06/23/2017
pnp.series.title: Cloud Design Patterns
ms.openlocfilehash: 26e5fe0bc05bff7b9fb684795a2de3b57d945ae0
ms.sourcegitcommit: b0482d49aab0526be386837702e7724c61232c60
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2017
---
# <a name="performance-and-scalability-patterns"></a>パフォーマンスとスケーラビリティのパターン

[!INCLUDE [header](../../_includes/header.md)]

パフォーマンスは、指定された期間内で任意のアクションを実行するシステムの応答性を示します。一方、スケーラビリティは、パフォーマンスに影響を与えずに負荷の増加に対応できる、またはすぐに追加できる使用可能なリソースに対するシステムの能力です。 通常、クラウド アプリケーションが直面するワークロードやアクティビティのピークは変動しています。 これらを予測することは、特にマルチテナント シナリオではほとんど不可能です。 代わりに、アプリケーションは、要求のピークに対応できるように制限範囲内でスケールアウトし、要求が減少するとスケールインできることが必要です。 スケーラビリティは、コンピューティング インスタンスだけではなく、データ ストレージやメッセージング インフラストラクチャなど、他の要素にとっても重要です。

| パターン | 概要 |
| ------- | ------- |
| [キャッシュアサイド](../cache-aside.md) | オンデマンドでデータをデータ ストアからキャッシュに読み込みます |
| [CQRS](../cqrs.md) | 個別のインターフェイスを使用して、データを更新する操作とデータを読み取る操作を分離します。 |
| [イベント ソース](../event-sourcing.md) | 追加専用ストアを使用して、ドメイン内のデータに実行されるアクションを記述する一連のイベントすべてを記録します。 |
| [テーブルのインデックス作成](../index-table.md) | クエリで頻繁に参照されるデータ ストア内のフィールドにインデックスを作成します。 |
| [具体化されたビュー](../materialized-view.md) | 必要なクエリ操作に対してデータのフォーマットが適していない場合に、1 つ以上のデータ ストアのデータについてあらかじめデータが移入されたビューを生成します。 |
| [優先順位キュー](../priority-queue.md) | サービスに送信される要求に優先順位を設定し、優先順位の高い要求から順番に受信および処理されるようにします。 |
| [キュー ベースの負荷平準化](../queue-based-load-leveling.md) | タスクとそのタスクが呼び出すサービスとの間でバッファーとして機能するキューを使用して、断続的な大きい負荷を平準化します。 |
| [シャーディング](../sharding.md) | データ ストアを水平方向のパーティションまたはシャードのセットに分割します。 |
| [静的コンテンツ ホスティング](../static-content-hosting.md) | 静的なコンテンツを、クライアントに直接配信できクラウドベースのストレージ サービスにデプロイします。 |
| [調整](../throttling.md) | アプリケーションのインスタンス、個々のテナント、またはサービス全体によって使用されるリソースの使用量を制御します。 |