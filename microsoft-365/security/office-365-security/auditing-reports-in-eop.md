---
title: スタンドアロン EOP の監査レポート
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 管理者は、Exchange Online Protection (EOP) で使用できる管理者監査レポートについて学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 08432f97d196df8b661d63a5d4cdf3680b78e070
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921290"
---
# <a name="auditing-reports-in-standalone-eop"></a>スタンドアロン EOP の監査レポート

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
-  [Exchange Online Protection スタンドアロン](exchange-online-protection-overview.md)

Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、監査レポートを使用すると、組織の規制、コンプライアンス、訴訟の要件を満たすのに役立ちます。 いつでも監査レポートを取得して、EOP 構成に加えられた変更を確認できます。 これらのレポートの構成に関する問題のトラブルシューティングを行うか、セキュリティ関連やコンプライアンス関連の問題の原因を見つけることができます。

スタンドアロン EOP では、次の 2 つの監査レポートを使用できます。

- **管理者役割グループ レポート**: 管理者役割グループ レポートでは、ユーザーが管理者役割グループのメンバーシップに追加または削除された場合に表示できます。 このレポートを使用して、組織内のユーザーに割り当てられた管理アクセス許可の変更を監視できます。 詳細については、「スタンドアロン [EOP で管理者役割グループ レポートを実行する」を参照してください](run-an-administrator-role-group-report-in-eop-eop.md)。

- **管理者監査ログ**: 管理者監査ログには、管理者または管理者特権を持つユーザーによる (スタンドアロン EOP PowerShell コマンドレットに基づく) すべてのアクションが記録されます。 詳細については [、「Exchange Online で管理者監査ログを表示する」を参照してください](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log)。