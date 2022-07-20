---
title: フィッシングメール攻撃の例
description: フィッシング攻撃の分析例を示します。
keywords: インシデント、アラート、調査、相関、攻撃、マシン、デバイス、ユーザー、複数の ID、ID、メールボックス、メール、365、Microsoft、M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-firstincident
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: dcf620cfaeb1d33665538d16d080e72745b96e42
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2022
ms.locfileid: "66892910"
---
# <a name="example-of-a-phishing-email-attack"></a>フィッシングメール攻撃の例

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defenderは、電子メールで配信された悪意のある添付ファイルを検出するのに役立ちます。 [Office 365 セキュリティとコンプライアンス センター](https://protection.office.com/)はMicrosoft 365 Defenderと統合されているため、セキュリティ アナリストは、電子メールの添付ファイルなど、Office 365からの脅威を可視化できます。

たとえば、アナリストに多段階のインシデントが割り当てられたとします。
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="多段階のインシデント" lightbox="../../media/first-incident-path-phishing/first-incident-phishing-incident.png":::

インシデントの [**アラート**] タブに、Defender for Office 365とMicrosoft Defender for Cloud Appsからのアラートが表示されます。 アナリストは、電子メール メッセージのアラートを選択して、Defender for Office 365 アラートにドリルダウンできます。 アラートの詳細がサイド ウィンドウに表示されます。

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="電子メール アラート" lightbox="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png":::
 
さらに下にスクロールすると、影響を受けた悪意のあるファイルとユーザーを示す詳細情報が表示されます。

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="電子メール アラートのユーザーとファイルの影響" lightbox="../../media/first-incident-path-phishing/first-incident-phishing-impact.png":::
  
[ **アラートを開く] ページ** を選択すると、リンクを選択することでさまざまな情報をより詳細に表示できる特定のアラートが表示されます。 実際の電子メール メッセージは、パネルの下部にある **エクスプローラーで [メッセージの表示** ] を選択して表示できます。
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="アラートの詳細" lightbox="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png"::: 

これにより、アナリストは、電子メールの件名、受信者、送信者、およびその他の情報が表示される脅威管理ページに移動します。 **特別なアクション** の **下の ZAP** は、ゼロ時間の自動消去機能が実装されたことをアナリストに伝えます。 ZAP は、組織全体のメールボックスから悪意のあるメッセージとスパム メッセージを自動的に検出して削除します。 詳細については、「[Exchange Online のゼロアワー自動消去 (ZAP)](../office-365-security/zero-hour-auto-purge.md)」を参照してください。

[アクション] を選択すると、特定のメッセージに対して他の **アクションを** 実行できます。 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="電子メール メッセージに対して実行できるその他のアクション" lightbox="../../media/first-incident-path-phishing/first-incident-phishing-actions.png"::: 

## <a name="next-step"></a>次の手順

[ID ベースの攻撃](first-incident-path-identity.md)調査パスを参照してください。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの調査](investigate-incidents.md)
- [インシデントの管理](manage-incidents.md)
