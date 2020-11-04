---
title: メールフローダッシュボードのトップドメインメールフローのステータスの洞察
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードにある上位ドメインのメールフロー状態の洞察を使用して、電子メールドメイン内の MX レコードに関連するメールフローの問題のトラブルシューティングを行う方法を学習できます。
ms.openlocfilehash: d4abc311e96df87894d5f059328f1a16a00190b8
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877512"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターでの上位ドメインメールフローのステータスの洞察

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[セキュリティ & コンプライアンスセンター](https://protection.office.com)の [メールフローダッシュボード](mail-flow-insights-v2.md)にある **上位ドメインメールフローの状態** に関する洞察は、メールフローの観点から、組織のドメインの現在の状態を示しています。 この洞察により、* *_メールフローに影響を与える_* ドメインを特定してトラブルシューティングするのに役立ちます。 (たとえば、外部電子メールを受信できない)、特にドメインの有効期限、または間違った MX レコードがあるドメイン。

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードのトップドメインフロー状態ウィジェット](../../media/mfi-top-domain-mail-flow-status-widget.png)

ウィジェットの [_ *View details* ] をクリックすると、 **ドメイン状態** ポップアップが表示され、各ドメインの状態の詳細がわかります。

- **ドメイン**
- **以前の MX レコード**
- **現在の MX レコード**
- **受信した電子メールの状態**
- **ドメインの状態** : 緑のチェックマークは、現在の MX レコード (ウィジェットをクリックしたとき) がレコードに設定されている値と一致し、ドメインが過去2時間以内に電子メールを受信したことを示します。

  赤の X は、MX レコードが変更されたこと、および過去6時間以内にドメインがメールを受信していないことを示します。 これは、ドメインの有効期限が切れているか、MX レコードが正しく更新されていないことを示している可能性があります。 ドメインレジストラーまたは DNS ホスティングサービスを使用して、ドメインの有効期限が切れていないか、またはドメインの MX レコードが正しくないかどうかを確認します。

[ **詳細表示** ] をクリックすると、他のドメインについても同じ情報が表示されます。

![上位ドメインのメールフローの状態に関する詳細ポップアップ](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a>関連項目

メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。
