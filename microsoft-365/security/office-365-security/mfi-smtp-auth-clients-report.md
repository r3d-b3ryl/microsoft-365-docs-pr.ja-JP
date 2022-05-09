---
title: SMTP 認証クライアントの分析情報とレポート (メール フロー ダッシュボード)
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで SMTP 認証分析情報とレポートを使用して、認証された SMTP (SMTP AUTH) を使用して電子メール メッセージを送信する組織内のメール送信者を監視する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8c2152820e7f3d5dbf04534e5f0b0fec344ecc7b
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474995"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>SMTP 認証クライアントのセキュリティ & コンプライアンス センターでの分析情報とレポート

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[メール フロー ダッシュボード](mail-flow-insights-v2.md)の **SMTP 認証クライアント** の分析情報と [、セキュリティ & コンプライアンス センター](https://protection.office.com)の関連 [する SMTP 認証クライアント レポート](#smtp-auth-clients-report)では、組織内のユーザーまたはシステム アカウントによる SMTP AUTH クライアント送信プロトコルの使用が強調表示されます。 このレガシ プロトコル (エンドポイント smtp.office365.com を使用) は基本認証のみを提供し、侵害されたアカウントが電子メールを送信するために使用される可能性があります。 分析情報とレポートを使用すると、SMTP AUTH 電子メール送信の異常なアクティビティを確認できます。 また、SMTP AUTH を使用するクライアントまたはデバイスの TLS 使用状況データも表示されます。

このウィジェットは、過去 7 日間に SMTP 認証プロトコルを使用したユーザーまたはサービス アカウントの数を示します。

:::image type="content" source="../../media/mfi-smtp-auth-clients-report-widget.png" alt-text="セキュリティ & コンプライアンス センターのメール フロー ダッシュボードの SMTP 認証クライアント ウィジェット" lightbox="../../media/mfi-smtp-auth-clients-report-widget.png":::

ウィジェットでメッセージの数をクリックすると、 **SMTP 認証クライアント** のポップアップが表示されます。 ポップアップは、過去 1 週間の TLS 使用量とボリュームの集計ビューを提供します。

:::image type="content" source="../../media/mfi-smtp-auth-clients-report-details.png" alt-text="メール フロー ダッシュボードで SMTP 認証クライアント ウィジェットをクリックした後の詳細ポップアップ" lightbox="../../media/mfi-smtp-auth-clients-report-details.png":::

次のセクションで説明するように、[ **SMTP 認証クライアント] レポート** のリンクをクリックして SMTP 認証クライアント レポートに移動できます。

## <a name="smtp-auth-clients-report"></a>SMTP Auth クライアントのレポート

### <a name="report-view-for-the-smtp-auth-clients-report"></a>SMTP 認証クライアント レポートのレポート ビュー

既定では、レポートには過去 7 日間のデータが表示されますが、データは過去 90 日間使用できます。

概要セクションには、次のグラフが含まれています。

- **データの表示方法: ボリュームの送信**: 既定では、すべてのドメインから送信された SMTP 認証クライアント メッセージの数がグラフに表示されます ([**データの表示: すべての送信者ドメイン** が既定で選択されています])。 [ **データの表示** ] をクリックし、ドロップダウン リストから送信者ドメインを選択することで、結果を特定の送信者ドメインにフィルター処理できます。 特定のデータ ポイント (日) をポイントすると、メッセージの数が表示されます。

  :::image type="content" source="../../media/mfi-smtp-auth-clients-report-sending-volume-view.png" alt-text="セキュリティ & コンプライアンス センターの SMTP 認証クライアント レポートの [ボリュームの送信] ビュー" lightbox="../../media/mfi-smtp-auth-clients-report-sending-volume-view.png":::

- **データの表示: TLS 使用量**: グラフには、選択した期間中のすべての SMTP 認証クライアント メッセージの TLS 使用量の割合が表示されます。 このグラフを使用すると、古いバージョンの TLS をまだ使用しているユーザーとシステム アカウントを特定してアクションを実行できます。

  :::image type="content" source="../../media/mfi-smtp-auth-clients-report-tls-usage-view.png" alt-text="セキュリティ & コンプライアンス センターの SMTP 認証クライアント レポートの TLS 使用状況ビュー" lightbox="../../media/mfi-smtp-auth-clients-report-tls-usage-view.png":::

レポート ビューで [**フィルター]** をクリックすると、開始日と **終了日** で **日付** 範囲を指定できます。

[ **レポートの要求]** をクリックして、電子メール メッセージでレポートのより詳細なバージョンを受信します。 レポートを受け取る日付範囲と受信者を指定できます。

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>SMTP 認証クライアント レポートの詳細テーブル ビュー

[ **詳細テーブルの表示**] をクリックした場合、表示される情報は、目的のグラフによって異なります。

- **データの表示: ボリュームの送信**: 次の情報を表に示します。

  - **[送信者のアドレス]**
  - **メッセージ数**

  行を選択すると、同じ詳細がポップアップに表示されます。

- **データを表示する方法: TLS 使用量**: 次の情報を表に示します。

  - **[送信者のアドレス]**
  - **TLS1.0%**<sup>\*</sup>
  - **TLS1.1%**<sup>\*</sup>
  - **TLS1.2%**<sup>\*</sup>
  - **メッセージ数**

  <sup>\*</sup> この列には、送信者からのメッセージの割合と数の両方が表示されます。

詳細テーブル ビューで [**フィルター]** をクリックすると、開始日と **終了日** で **日付** 範囲を指定できます。

行を選択すると、同様の詳細がポップアップに表示されます。

:::image type="content" source="../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png" alt-text="SMTP 認証クライアント レポートの TLS 使用状況ビューの詳細テーブルからの詳細ポップアップ" lightbox="../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png":::

[ **レポートの要求]** をクリックして、電子メール メッセージでレポートのより詳細なバージョンを受信します。 レポートを受け取る日付範囲と受信者を指定できます。

レポート ビューに戻るには、[レポートの **表示**] をクリックします。

## <a name="related-topics"></a>関連項目

メール フロー ダッシュボードのその他の分析情報については、 [セキュリティ & コンプライアンス センターのメール フロー分析情報に関する](mail-flow-insights-v2.md)ページを参照してください。
