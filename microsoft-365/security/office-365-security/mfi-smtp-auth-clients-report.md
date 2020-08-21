---
title: メール フロー ダッシュボードの SMTP Auth クライアントインサイトとレポート
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで SMTP Auth insight を使用してレポートし、認証済み SMTP (SMTP AUTH) を使用してメール メッセージを送信する、組織内のメール送信者を監視する方法を学習できます。
ms.openlocfilehash: 65e5569bcd79caef071ee2103d18a4e985c19dbb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826871"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターの SMTP Auth クライアントのインサイト& レポート

**メール フローのダッシュボードおよび**関連する SMTP Auth[クライアント](mail-flow-insights-v2.md)レポートの[SMTP Auth クライアントから、組織内](#smtp-auth-clients-report)のユーザーまたはシステム アカウントでの SMTP AUTH クライアント送信プロトコルの使用状況を強調表示します。 このレガシ プロトコル (エンドポイント smtp.office365.com を使用する) は基本認証のみを提供し、侵害されたアカウントが電子メールを送信するために使用するのを受け付けします。 インサイトとレポートでは、SMTP AUTH メールを送信するための異形式のアクティビティをチェックできます。 また、SMTP AUTH を使用したクライアントまたはデバイスの TLS 使用状況データも示しています。

ウィジェットは、過去 7 日間の SMTP Auth プロトコルを使用したユーザーまたはサービス アカウントの数を示します。

![セキュリティ センター センターのメール フロー ダッシュボードの SMTP Auth クライアント &イジェット](../../media/mfi-smtp-auth-clients-report-widget.png)

ウィジェット上のメッセージ数をクリックすると **、SMTP Auth クライアントのポップ** アップが表示されます。 ポップアップでは、過去 1 週間の TLS 使用状況とボリュームの集計ビューが提供されます。

![[メール フロー ダッシュボード] で SMTP Auth クライアント ウィジェットをクリックした後の詳細ポップアップ](../../media/mfi-smtp-auth-clients-report-details.png)

SMTP Auth クライアント レポート **リンクをクリックすると** 、次のセクションの説明に示されている SMTP Auth クライアント レポートに移動できます。

## <a name="smtp-auth-clients-report"></a>SMTP Auth クライアントのレポート

### <a name="report-view-for-the-smtp-auth-clients-report"></a>SMTP Auth クライアント レポートのレポート ビュー

既定では、レポートには最も期間 7 日間のデータが表示されますが、過去 90 日間のデータが取得可能になります。

概要セクションには、次のグラフが含まれます。

- **データの表示: ボリュームの送信**: 既定では、すべてのドメインから送信された SMTP Auth クライアント メッセージの数がグラフに表示されます **([表示: 既定ではすべての送信者ドメイン** ] が選択されています)。 特定の送信者ドメインに結果をフィルターするには、[ **データの** 表示] をクリックし、ドロップダウン リストから送信者ドメインを選択します。 特定のデータ ポイントをポイントする場合は、メッセージ数が表示されます。

  ![コンプライアンス センターの SMTP Auth クライアント レポートでのボリューム & ビューの送信](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **データの閲覧元: TLS 使用**率: 選択した期間中のすべての SMTP Auth クライアント メッセージに対する TLS 使用率がグラフに示されます。 このグラフを使用すると、ユーザーおよびシステム アカウントを特定して、以前のバージョンの TLS を使用しているユーザー アカウントを特定してアクションを実行できます。

  ![セキュリティ コンプライアンス センターの SMTP Auth クライアント レポートの TLS 使用&ビュー](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

レポート ビューで **[フィルター** ] をクリックすると、開始日と終了日で**日付範囲****を指定できます**。

[ **要求] レポートを** クリックすると、メール メッセージでレポートの詳細バージョンが表示されます。 レポートを受信する日付範囲と受信者を指定できます。

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>SMTP Auth クライアント レポートの詳細テーブル ビュー

[詳細の **表示] テーブルを**クリックした場合に表示される情報は、表示しているグラフによって異なるためです。

- **データの表示: Sending volume:** 次の情報が表に表示されています。

  - **[送信者のアドレス]**
  - **メッセージ数**

  行を選択すると、詳細と同じ詳細がポップアップに表示されます。

- **データの表示元: TLS の使用**方法: 次の情報を表に示します。

  - **[送信者のアドレス]**
  - **TLS1.0%**<sup>\*</sup>
  - **TLS1.1%**<sup>\*</sup>
  - **TLS1.2%**<sup>\*</sup>
  - **メッセージ数**

  <sup>\*</sup> この列には、送信者からのメッセージの割合と数の両方が表示されます。

詳細テーブル ビュー**の [** フィルター] をクリックすると、開始日と終了日で**日付範囲****を指定できます**。

行を選択すると、同様の詳細がポップアップに表示されます。

![SMTP Auth クライアント レポートの TLS 使用状況ビューの詳細テーブルからの詳細ポップアップ](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

[ **要求] レポートを** クリックすると、メール メッセージでレポートの詳細バージョンが表示されます。 レポートを受信する日付範囲と受信者を指定できます。

レポート ビューに戻るには、[レポートの表示] **をクリックします**。

## <a name="related-topics"></a>関連トピック

メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。
