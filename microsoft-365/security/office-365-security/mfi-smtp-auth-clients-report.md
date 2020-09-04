---
title: メールフローダッシュボードの SMTP 認証クライアントの洞察とレポート
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
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードで SMTP 認証の洞察とレポートを使用して、組織内で、認証済みの SMTP (SMTP AUTH) を使用して電子メールメッセージを送信する電子メール送信者を監視する方法を学習できます。
ms.openlocfilehash: 4123edcfa08e31217dcd6a29186492bc036fa7a0
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357436"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターでの SMTP 認証クライアントの洞察とレポート

[メールフローのダッシュボード](mail-flow-insights-v2.md)と、[セキュリティ & コンプライアンスセンター](https://protection.office.com)で報告される smtp auth**クライアントの**[レポート](#smtp-auth-clients-report)では、組織内のユーザーまたはシステムアカウントによる smtp auth クライアント送信プロトコルの使用が強調されています。 この従来のプロトコル (エンドポイント smtp.office365.com を使用します) は基本認証のみを提供し、侵害されたアカウントが電子メールを送信するために使用されやすくなります。 洞察とレポートを使用すると、SMTP 認証の電子メールの送信に関する異常な動作を確認できます。 また、SMTP 認証を使用するクライアントまたはデバイスの TLS 使用状況データも表示されます。

ウィジェットは、過去7日間に SMTP 認証プロトコルを使用したユーザーまたはサービスアカウントの数を示します。

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードの SMTP 認証クライアントウィジェット](../../media/mfi-smtp-auth-clients-report-widget.png)

ウィジェットのメッセージ数をクリックすると、[ **SMTP Auth clients** ] ポップアップが表示されます。 フライアウトは、過去1週間の TLS 使用量とボリュームを集約したビューを提供します。

![メールフローダッシュボードの SMTP 認証クライアントウィジェットをクリックした後の詳細ポップアップ](../../media/mfi-smtp-auth-clients-report-details.png)

[ **Smtp auth clients レポート** ] リンクをクリックすると、次のセクションで説明されているように、smtp auth clients レポートに移動できます。

## <a name="smtp-auth-clients-report"></a>SMTP Auth クライアントのレポート

### <a name="report-view-for-the-smtp-auth-clients-report"></a>SMTP 認証クライアントレポートのレポートビュー

既定では、レポートには過去7日間のデータが表示されますが、データは過去90日間で利用可能です。

概要セクションには、次のグラフが含まれています。

- **データの表示: 送信ボリューム**: 既定では、すべてのドメインから送信された SMTP Auth クライアントメッセージの数 ([**データの表示: 既定ではすべての送信者ドメイン** が選択されています)] を示しています。 結果を特定の送信者のドメインにフィルター処理するには、ドロップダウンリストから [ **データの表示]** をクリックし、送信者のドメインを選択します。 特定のデータポイント (日単位) をポイントすると、メッセージ数が表示されます。

  ![セキュリティ & コンプライアンスセンターの SMTP 認証クライアントレポートでのボリューム表示の送信](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **データの表示方法: TLS 使用法**: 選択した期間におけるすべての SMTP Auth クライアントメッセージの tls 使用率を示します。 このグラフでは、以前のバージョンの TLS を使用しているユーザーとシステムアカウントを識別し、アクションを実行することができます。

  ![セキュリティ & コンプライアンスセンターの SMTP 認証クライアントレポートの TLS 使用法の表示](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

レポートビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。

[ **要求レポート** ] をクリックして、レポートの詳細バージョンを電子メールメッセージで受信します。 レポートを受信する日付の範囲と受信者を指定できます。

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>SMTP Auth clients レポートの詳細表ビュー

[ **詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。

- **データの表示: 送信ボリューム**: 次の情報が表に表示されます。

  - **[送信者のアドレス]**
  - **メッセージ数**

  行を選択すると、同じ詳細がフライアウトに表示されます。

- **データの表示方法: TLS 使用法**: 次の情報を表に示します。

  - **[送信者のアドレス]**
  - **TLS 1.0%**<sup>\*</sup>
  - **TLS 1.1%**<sup>\*</sup>
  - **TLS 1.2%**<sup>\*</sup>
  - **メッセージ数**

  <sup>\*</sup> この列には、送信者からのメッセージの割合と数が表示されます。

詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。

行を選択すると、同様の詳細がフライアウトに表示されます。

![SMTP Auth clients レポートの [TLS usage] ビューの詳細表からの詳細ポップアップ](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

[ **要求レポート** ] をクリックして、レポートの詳細バージョンを電子メールメッセージで受信します。 レポートを受信する日付の範囲と受信者を指定できます。

レポートビューに戻るには、[ **レポートの表示**] をクリックします。

## <a name="related-topics"></a>関連項目

メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。
