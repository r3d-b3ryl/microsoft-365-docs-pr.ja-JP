---
title: メール フロー ダッシュボードのトップ ドメイン メール フローの状態に関する分析情報
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで、トップ ドメインのメール フロー状態の分析情報を使用して、MX レコードに関連するメール フローの問題をトラブルシューティングする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: df0f571d29d72b23e7b2e210b61a4fb1676175aa
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150209"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターのトップ ドメイン メール フロー&分析情報

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

セキュリティ **/コンプライアンス センターの**[メール [](mail-flow-insights-v2.md)フロー] ダッシュボード [](https://protection.office.com)の [トップ ドメイン のメール フローの状態] の分析情報&組織の現在のメール フローの状態が表示されます。

この分析情報は、メール フローの問題が発生しているドメインの特定と ***トラブルシューティングに役立*** ちます。 たとえば、ドメインの有効期限が切れているか、ドメインの MX レコードが正しくないため、ドメインは外部電子メールを受信できません。

![セキュリティ/コンプライアンス センターのメール フロー ダッシュボードの&状態ウィジェット](../../media/mfi-top-domain-mail-flow-status-widget.png)

ウィジェットの [**詳細の** 表示] をクリックすると、各ドメインの状態に関する詳細を表示するドメイン状態のフライアウトが表示されます。

- **ドメイン**
- **以前の MX レコード**
- **現在の MX レコード**
- **電子メールの受信状態**
- **ドメインの** 状態 : 緑色のチェック マークは、(ウィジェットをクリックした時点で) 現在の MX レコードが記録されている値と一致し、ドメインが過去 2 時間以内にメールを受信したかどうかを示します。

  赤い X は MX レコードが変更され、過去 6 時間以内にドメインが電子メールを受信しきっていない状態を示します。 これは、ドメインの有効期限が切れているか、MX レコードが正しく更新されていないことを示している可能性があります。 ドメイン レジストラーまたは DNS ホスティング サービスに確認して、ドメインの有効期限が切れているか、ドメインの MX レコードが正しくないか確認してください。

[詳細を **表示] をクリック** すると、他のドメインの同じ情報を表示できます。

![トップ ドメイン メール フローの状態の分析情報の詳細フライアウト](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>こちらもご覧ください

メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。
