---
title: メール フロー ダッシュボードの上位ドメインのメール フローの状態分析情報
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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで上位ドメインのメール フローの状態分析情報を使用して、MX レコードに関連するメール フローの問題をトラブルシューティングする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3994859c1d5a4e0026f61dcc24a9735c6122ad15
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64465423"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>セキュリティ & コンプライアンス センターの上位ドメイン メール フローの状態分析情報

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[セキュリティ & コンプライアンス センター](https://protection.office.com)の [[メール フロー] ダッシュボード](mail-flow-insights-v2.md)の **[上位ドメインのメール フローの状態** 分析情報] には、組織の現在のメール フローの状態が表示されます。

この分析情報は、 ***メール フロー*** の問題が発生しているドメインを特定し、トラブルシューティングするのに役立ちます。 たとえば、ドメインの有効期限が切れているか、ドメインに正しくない MX レコードがあるため、ドメインは外部メールを受信できません。

:::image type="content" source="../../media/mfi-top-domain-mail-flow-status-widget.png" alt-text="セキュリティ & コンプライアンス センターのメール フロー ダッシュボードの上位ドメイン フローの状態ウィジェット" lightbox="../../media/mfi-top-domain-mail-flow-status-widget.png":::

ウィジェットで [ **詳細の表示** ] をクリックすると、 **ドメインの状態** ポップアップが表示され、各ドメインの状態の詳細が表示されます。

- **ドメイン**
- **以前の MX レコード**
- **現在の MX レコード**
- **電子メール受信状態**
- **ドメインの状態**: 緑色のチェック マークは、現在の MX レコード (ウィジェットをクリックした時点) がレコードの値と一致し、ドメインが過去 2 時間の間に電子メールを受信したことを示します。

  赤い X は MX レコードが変更されたことを示し、ドメインは過去 6 時間の間にメールを受け取っていない。 これは、ドメインの有効期限が切れているか、MX レコードが正しく更新されていないことを示している可能性があります。 ドメインレジストラーまたは DNS ホスティング サービスに問い合わせて、ドメインの有効期限が切れているかどうか、またはドメインの MX レコードが正しくないかどうかを確認します。

[ **その他** のドメインの表示] をクリックすると、同じ情報が表示されます。

:::image type="content" source="../../media/mfi-top-domain-mail-flow-status-view-details.png" alt-text="上位ドメインのメール フローの状態分析情報の詳細ポップアップ" lightbox="../../media/mfi-top-domain-mail-flow-status-view-details.png":::

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードのその他の分析情報については、 [セキュリティ & コンプライアンス センターのメール フロー分析情報に関する](mail-flow-insights-v2.md)ページを参照してください。
