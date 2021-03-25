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
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205547"
---
# <a name="auditing-reports-in-standalone-eop"></a><span data-ttu-id="c9512-103">スタンドアロン EOP の監査レポート</span><span class="sxs-lookup"><span data-stu-id="c9512-103">Auditing reports in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c9512-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c9512-104">**Applies to**</span></span>
-  [<span data-ttu-id="c9512-105">Exchange Online Protection スタンドアロン</span><span class="sxs-lookup"><span data-stu-id="c9512-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="c9512-106">Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、監査レポートを使用すると、組織の規制、コンプライアンス、訴訟の要件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c9512-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, auditing reports can help you meet regulatory, compliance, and litigation requirements for your organization.</span></span> <span data-ttu-id="c9512-107">いつでも監査レポートを取得して、EOP 構成に加えられた変更を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c9512-107">You can obtain auditing reports at any time to determine the changes that have been made to your EOP configuration.</span></span> <span data-ttu-id="c9512-108">これらのレポートの構成に関する問題のトラブルシューティングを行うか、セキュリティ関連やコンプライアンス関連の問題の原因を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="c9512-108">These reports can help you troubleshoot configuration issues or find the cause of security-related or compliance-related problems.</span></span>

<span data-ttu-id="c9512-109">スタンドアロン EOP では、次の 2 つの監査レポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9512-109">There are two auditing reports available in standalone EOP:</span></span>

- <span data-ttu-id="c9512-110">**管理者役割グループ レポート**: 管理者役割グループ レポートでは、ユーザーが管理者役割グループのメンバーシップに追加または削除された場合に表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9512-110">**Administrator role group report**: The administrator role group report lets you view when a user is added to or removed from membership in an administrator role group.</span></span> <span data-ttu-id="c9512-111">このレポートを使用して、組織内のユーザーに割り当てられた管理アクセス許可の変更を監視できます。</span><span class="sxs-lookup"><span data-stu-id="c9512-111">You can use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span> <span data-ttu-id="c9512-112">詳細については、「スタンドアロン [EOP で管理者役割グループ レポートを実行する」を参照してください](run-an-administrator-role-group-report-in-eop-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="c9512-112">For more information, see [Run an administrator role group report in standalone EOP](run-an-administrator-role-group-report-in-eop-eop.md).</span></span>

- <span data-ttu-id="c9512-113">**管理者監査ログ**: 管理者監査ログには、管理者または管理者特権を持つユーザーによる (スタンドアロン EOP PowerShell コマンドレットに基づく) すべてのアクションが記録されます。</span><span class="sxs-lookup"><span data-stu-id="c9512-113">**Administrator audit log**: The administrator audit log records any action (based on standalone EOP PowerShell cmdlets) by an admin or a user with administrative privileges.</span></span> <span data-ttu-id="c9512-114">詳細については [、「Exchange Online で管理者監査ログを表示する」を参照してください](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log)。</span><span class="sxs-lookup"><span data-stu-id="c9512-114">For more information, see [View the Administrator Audit Log in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log).</span></span>