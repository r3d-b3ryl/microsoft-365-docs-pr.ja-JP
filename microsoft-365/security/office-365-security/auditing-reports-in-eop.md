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
description: 管理者は Exchange Online Protection (EOP) で利用できる管理者監査レポートについて学習できます。
ms.openlocfilehash: ab2c1af7197094b456d8e1b4151dd42791d992a1
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825787"
---
# <a name="auditing-reports-in-standalone-eop"></a><span data-ttu-id="a1311-103">スタンドアロン EOP の監査レポート</span><span class="sxs-lookup"><span data-stu-id="a1311-103">Auditing reports in standalone EOP</span></span>

<span data-ttu-id="a1311-104">Exchange Online メールボックスを使用していないスタンドアロン Exchange Online Protection (EOP) 組織では、監査レポートは組織の規制、コンプライアンス、および訴訟に関する要件を満たすために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a1311-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, auditing reports can help you meet regulatory, compliance, and litigation requirements for your organization.</span></span> <span data-ttu-id="a1311-105">いつでも監査レポートを取得して、EOP 構成に加えられた変更を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a1311-105">You can obtain auditing reports at any time to determine the changes that have been made to your EOP configuration.</span></span> <span data-ttu-id="a1311-106">これらのレポートの構成に関する問題のトラブルシューティングを行うか、セキュリティ関連やコンプライアンス関連の問題の原因を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="a1311-106">These reports can help you troubleshoot configuration issues or find the cause of security-related or compliance-related problems.</span></span>

<span data-ttu-id="a1311-107">スタンドアロン EOP では、2 つの監査レポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1311-107">There are two auditing reports available in standalone EOP:</span></span>

- <span data-ttu-id="a1311-108">**管理者の役割グループ レポート**: 管理者役割グループ レポートにより、いつユーザーが管理者役割グループのメンバーシップに追加または削除されたかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a1311-108">**Administrator role group report**: The administrator role group report lets you view when a user is added to or removed from membership in an administrator role group.</span></span> <span data-ttu-id="a1311-109">このレポートを使用して、組織内のユーザーに割り当てられた管理アクセス許可の変更を監視できます。</span><span class="sxs-lookup"><span data-stu-id="a1311-109">You can use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span> <span data-ttu-id="a1311-110">詳細については、「スタンドアロン [EOP で管理者役割グループ レポートを実行する」を参照してください](run-an-administrator-role-group-report-in-eop-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="a1311-110">For more information, see [Run an administrator role group report in standalone EOP](run-an-administrator-role-group-report-in-eop-eop.md).</span></span>

- <span data-ttu-id="a1311-111">**管理者監査ログ**: 管理者監査ログ : 管理者または管理者特権を持つユーザーによる (スタンドアロンの EOP PowerShell コマンドレットに基づく) 操作を記録します。</span><span class="sxs-lookup"><span data-stu-id="a1311-111">**Administrator audit log**: The administrator audit log records any action (based on standalone EOP PowerShell cmdlets) by an admin or a user with administrative privileges.</span></span> <span data-ttu-id="a1311-112">詳細については [、Exchange Online で管理者監査ログを表示する」を参照してください](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log)。</span><span class="sxs-lookup"><span data-stu-id="a1311-112">For more information, see [View the Administrator Audit Log in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log).</span></span>
