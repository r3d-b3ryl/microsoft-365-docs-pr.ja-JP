---
title: メール フロー ダッシュボードの上位ドメインのメール フローの状態に関する分析情報
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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで上位ドメインのメール フローの状態のインサイトを使用して、メール ドメイン内の MX レコードに関連するメール フロー問題のトラブルシューティングを行う方法を学習できます。
ms.openlocfilehash: 9640d5e37932efeb7c0c8f8c56d0a15bc7f07e5b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827017"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>セキュリティ センターの上位ドメインのメール フローの状態&分析情報

セキュリティ &**コンプライアンス センターの**メール フロー ダッシュボード[Mail flow dashboard](mail-flow-insights-v2.md)で上位ドメインのメール フロー状態の分析情報は、メール フローの点で組織のドメインの現在の状態を示します。 この分析情報は、問題に影響を与えるメール フロー (外部メールを受信できない***mail flow impacting***など) を特定してトラブルシューティングする際に役立ちます。特に、ドメインの有効期限または MX レコードが正しくないドメイン。

![セキュリティ/コンプライアンス センターのメール フロー ダッシュボードの上位ドメイン フローの状態ウィジ&イジェット](../../media/mfi-top-domain-mail-flow-status-widget.png)

ウィジェ **ットの [** 詳細の表示] をクリックすると、 **各ドメイン** の状態に関する詳細が [ドメインの状態] ポップアップに表示されます。

- **ドメイン**
- **以前の MX レコード**
- **現在の MX レコード**
- **メールの受信状態**
- **Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.

  赤い X は、MX レコードが変更されたことを示し、そのドメインが現在 6 時間前にメールを受信したことを示します。 これは、ドメインの有効期限が切れていること、または MX レコードが正しく更新されていないことを示している可能性があります。 ドメイン レジストラーか DNS ホスティング サービスに確認して、ドメインの有効期限が切れていないか、ドメインの MX レコードが正しくないかどうかを確認してください。

[詳細表示] **をクリックすると** 、その他のドメインに対して同じ情報が表示されます。

![[トップ ドメインのメール フロー状態] の詳細ポップアップ](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a>関連トピック

メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。
