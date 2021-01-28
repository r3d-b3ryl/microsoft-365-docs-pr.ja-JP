---
title: メール フロー ダッシュボードのトップ ドメイン メール フロー状態の分析情報
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
ms.openlocfilehash: 457675e7f32cd513f5593ede53a64aaef9d54904
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029908"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターのトップ ドメイン メール フロー&分析情報

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


セキュリティ **/コンプライアンス センター** の [メール [](mail-flow-insights-v2.md)フロー] ダッシュボード [](https://protection.office.com)の [トップ ドメインのメール フローの状態] の分析情報&、組織の現在のメール フローの状態が表示されます。

この分析情報は、* メール フロー _ の問題が発生しているドメインを特定 *_し、トラブルシューティングするのに_* 役立ちます。 たとえば、ドメインの有効期限が切れているか、ドメインの MX レコードが正しくないため、ドメインは外部電子メールを受信できません。

![セキュリティ/コンプライアンス センターのメール フロー ダッシュボードの&状態ウィジェット](../../media/mfi-top-domain-mail-flow-status-widget.png)

ウィジェットで _ *[詳細の表示*] *をクリックすると、各ドメインの状態に関する詳細を示す Domain ステータス フライアウトが表示されます。

- **ドメイン**
- **以前の MX レコード**
- **現在の MX レコード**
- **電子メールの受信状態**
- **ドメインの** 状態 : 緑色のチェック マークは、(ウィジェットをクリックした時点で) 現在の MX レコードが記録されている値と一致し、ドメインが過去 2 時間以内にメールを受信したかどうかを示します。

  赤い X は MX レコードが変更され、過去 6 時間以内にドメインが電子メールを受信しきっていない状態を示します。 これは、ドメインの有効期限が切れているか、MX レコードが正しく更新されていないことを示している可能性があります。 ドメイン レジストラーまたは DNS ホスティング サービスに確認して、ドメインの有効期限が切れているか、ドメインの MX レコードが正しくないか確認してください。

[詳細を **表示] をクリック** すると、他のドメインの同じ情報を表示できます。

![トップ ドメイン メール フローの状態の分析情報の詳細フライアウト](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。
