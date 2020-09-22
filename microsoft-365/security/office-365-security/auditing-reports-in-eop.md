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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 管理者は、Exchange Online Protection (EOP) で使用可能な管理者監査レポートについて学ぶことができます。
ms.openlocfilehash: 8e5175266cd964a2f2fb721a67f64e709661ce26
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200335"
---
# <a name="auditing-reports-in-standalone-eop"></a><span data-ttu-id="cd586-103">スタンドアロン EOP の監査レポート</span><span class="sxs-lookup"><span data-stu-id="cd586-103">Auditing reports in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cd586-104">Exchange Online メールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) 組織では、監査レポートを使用して、組織の法規制、コンプライアンス、および訴訟の要件を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="cd586-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, auditing reports can help you meet regulatory, compliance, and litigation requirements for your organization.</span></span> <span data-ttu-id="cd586-105">いつでも監査レポートを取得して、EOP 構成に加えられた変更を確認できます。</span><span class="sxs-lookup"><span data-stu-id="cd586-105">You can obtain auditing reports at any time to determine the changes that have been made to your EOP configuration.</span></span> <span data-ttu-id="cd586-106">これらのレポートの構成に関する問題のトラブルシューティングを行うか、セキュリティ関連やコンプライアンス関連の問題の原因を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="cd586-106">These reports can help you troubleshoot configuration issues or find the cause of security-related or compliance-related problems.</span></span>

<span data-ttu-id="cd586-107">スタンドアロン EOP では、次の2つの監査レポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cd586-107">There are two auditing reports available in standalone EOP:</span></span>

- <span data-ttu-id="cd586-108">**管理者の役割グループレポート**: 管理者の役割グループレポートでは、管理者の役割グループのメンバーシップに対してユーザーが追加または削除されたときに表示することができます。</span><span class="sxs-lookup"><span data-stu-id="cd586-108">**Administrator role group report**: The administrator role group report lets you view when a user is added to or removed from membership in an administrator role group.</span></span> <span data-ttu-id="cd586-109">このレポートを使用して、組織内のユーザーに割り当てられた管理アクセス許可の変更を監視できます。</span><span class="sxs-lookup"><span data-stu-id="cd586-109">You can use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span> <span data-ttu-id="cd586-110">詳細については、「 [スタンドアロン EOP で管理者の役割グループレポートを実行する](run-an-administrator-role-group-report-in-eop-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd586-110">For more information, see [Run an administrator role group report in standalone EOP](run-an-administrator-role-group-report-in-eop-eop.md).</span></span>

- <span data-ttu-id="cd586-111">**管理者監査ログ**: 管理者監査ログは、管理者または管理者特権を持つユーザーによって、スタンドアロンの EOP PowerShell コマンドレットに基づく操作を記録します。</span><span class="sxs-lookup"><span data-stu-id="cd586-111">**Administrator audit log**: The administrator audit log records any action (based on standalone EOP PowerShell cmdlets) by an admin or a user with administrative privileges.</span></span> <span data-ttu-id="cd586-112">詳細については、「 [Exchange Online で管理者監査ログを表示する](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd586-112">For more information, see [View the Administrator Audit Log in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log).</span></span>
