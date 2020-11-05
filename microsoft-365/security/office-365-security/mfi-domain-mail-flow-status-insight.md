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
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードにある上位ドメインのメールフロー状態の洞察を使用して、MX レコードに関連するメールフローの問題のトラブルシューティングを行う方法について説明します。
ms.openlocfilehash: 0d750ab4dbe5875796118086fae1d9119dc486f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920586"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターでの上位ドメインメールフローのステータスの洞察

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[セキュリティ & コンプライアンスセンター](https://protection.office.com)の [メールフローダッシュボード](mail-flow-insights-v2.md)にある **上位ドメインのメールフローの状態** に関する洞察は、組織の現在のメールフローの状態を示しています。

この洞察は、* *_メールフロー_* の問題が発生しているドメインを特定し、トラブルシューティングするのに役立つ情報です。 たとえば、ドメインの有効期限が切れているか、ドメインの MX レコードが正しくないため、ドメインは外部メールを受信できません。

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードのトップドメインフロー状態ウィジェット](../../media/mfi-top-domain-mail-flow-status-widget.png)

ウィジェットの [_ *View details* ] をクリックすると、 **ドメイン状態** ポップアップが表示され、各ドメインの状態の詳細がわかります。

- **ドメイン**
- **以前の MX レコード**
- **現在の MX レコード**
- **受信した電子メールの状態**
- **ドメインの状態** : 緑のチェックマークは、現在の MX レコード (ウィジェットをクリックしたとき) がレコードに設定されている値と一致し、ドメインが過去2時間以内に電子メールを受信したことを示します。

  赤の X は MX レコードが変更されたことを示し、ドメインは過去6時間以内に電子メールを受信していないことを示します。 これは、ドメインの有効期限が切れているか、MX レコードが正しく更新されていないことを示している可能性があります。 ドメインレジストラーまたは DNS ホスティングサービスを使用して、ドメインの有効期限が切れていないか、またはドメインの MX レコードが正しくないかどうかを確認します。

[ **詳細表示** ] をクリックすると、他のドメインについても同じ情報が表示されます。

![上位ドメインのメールフローの状態に関する詳細ポップアップ](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>関連項目

メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。
