---
title: 保管ロックを使用して、アイテム保持ポリシーと保持ラベル ポリシーへの変更を制限する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: アイテム保持ポリシーと保持ラベル ポリシーとともに保管ロックを使用して、規制要件を満たし、不正な管理者から保護します。
ms.openlocfilehash: 72f667b970b4257a3a540fb74a121c620892b56d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922531"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a><span data-ttu-id="a61fe-103">保管ロックを使用して、アイテム保持ポリシーと保持ラベル ポリシーへの変更を制限する</span><span class="sxs-lookup"><span data-stu-id="a61fe-103">Use Preservation Lock to restrict changes to retention policies and retention label policies</span></span>

><span data-ttu-id="a61fe-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="a61fe-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="a61fe-105">保管ロックは、アイテム保持ポリシーまたは保持ラベル ポリシーをロックして、グローバル管理者を含む誰もがポリシーをオフにしたり、ポリシーを削除したり、制限を緩和したりできないようにします。</span><span class="sxs-lookup"><span data-stu-id="a61fe-105">Preservation Lock locks a retention policy or retention label policy so that no one—including a global admin—can turn off the policy, delete the policy, or make it less restrictive.</span></span> <span data-ttu-id="a61fe-106">この構成は、規制要件のために必要になる場合があります。また、不正な管理者からの保護に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a61fe-106">This configuration might be needed for regulatory requirements and can help safeguard against rogue administrators.</span></span>

<span data-ttu-id="a61fe-107">保持ポリシーがロックされている場合:</span><span class="sxs-lookup"><span data-stu-id="a61fe-107">When a retention policy is locked:</span></span>

- <span data-ttu-id="a61fe-108">ポリシーを無効にしたり削除したりすることはできません</span><span class="sxs-lookup"><span data-stu-id="a61fe-108">No one can disable the policy or delete it</span></span>
- <span data-ttu-id="a61fe-109">場所は追加できますが、削除できません</span><span class="sxs-lookup"><span data-stu-id="a61fe-109">Locations can be added but not removed</span></span>
- <span data-ttu-id="a61fe-110">保持期間を延長することはできますが、短縮することはできません</span><span class="sxs-lookup"><span data-stu-id="a61fe-110">You can extend the retention period but not decrease it</span></span>

<span data-ttu-id="a61fe-111">保持ラベル ポリシーがロックされている場合:</span><span class="sxs-lookup"><span data-stu-id="a61fe-111">When a retention label policy is locked:</span></span>

- <span data-ttu-id="a61fe-112">ポリシーを無効にしたり削除したりすることはできません</span><span class="sxs-lookup"><span data-stu-id="a61fe-112">No one can disable the policy or delete it</span></span>
- <span data-ttu-id="a61fe-113">場所は追加できますが、削除できません</span><span class="sxs-lookup"><span data-stu-id="a61fe-113">Locations can be added but not removed</span></span>
- <span data-ttu-id="a61fe-114">ラベルは追加できますが、削除できません</span><span class="sxs-lookup"><span data-stu-id="a61fe-114">Labels can be added but not removed</span></span>

<span data-ttu-id="a61fe-115">つまり、ロックされたアイテム保持ポリシーを増やしたり延長したりすることは可能ですが、減らしたり、オフにしたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a61fe-115">In summary, a locked policy can be increased or extended, but it can't be reduced or turned off.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a61fe-116">アイテム保持ポリシーまたは保持ラベル ポリシーをロックする前に、その影響を理解し、それが組織に必要であるかどうかを確認することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="a61fe-116">Before you lock a retention policy or retention label policy, it's critical that you understand the impact and confirm whether it's required for your organization.</span></span> <span data-ttu-id="a61fe-117">たとえば、規制要件を満たす必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a61fe-117">For example, it might be needed to meet regulatory requirements.</span></span> <span data-ttu-id="a61fe-118">保管ロックを適用すると、管理者はこれらのポリシーを無効にすることも削除することもできなくなります。</span><span class="sxs-lookup"><span data-stu-id="a61fe-118">Administrators won't be able to disable or delete these policies after the preservation lock is applied.</span></span>

<span data-ttu-id="a61fe-119">[発行](create-apply-retention-labels.md)または[自動適用](apply-retention-labels-automatically.md)する[アイテム保持ポリシー](create-retention-policies.md)、または保持ラベル ポリシーを作成した後、保管ロックを構成します。</span><span class="sxs-lookup"><span data-stu-id="a61fe-119">Configure Preservation Lock after you've created a [retention policy](create-retention-policies.md), or a retention label policy that you [publish](create-apply-retention-labels.md) or [auto-apply](apply-retention-labels-automatically.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="a61fe-120">ラベル ポリシーをロックしても、管理者はロックされたポリシーに含まれているラベルの保持期間を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="a61fe-120">Locking a label policy doesn't prevent an administrator from reducing the retention period in a label that is included in the locked policy.</span></span> <span data-ttu-id="a61fe-121">アイテムを[規制レコード](records-management.md#records)としてマークするようにラベルを構成するときに、この要件を他の制限とともに満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="a61fe-121">That requirement, with other restrictions, can be met when you configure a label to mark items as a [regulatory record](records-management.md#records).</span></span>

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a><span data-ttu-id="a61fe-122">アイテム保持ポリシーまたは保持ラベル ポリシーをロックする方法</span><span class="sxs-lookup"><span data-stu-id="a61fe-122">How to lock a retention policy or retention label policy</span></span>

<span data-ttu-id="a61fe-123">保管ロックを使用する必要がある場合は、PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a61fe-123">You must use PowerShell if you need to use Preservation Lock.</span></span> <span data-ttu-id="a61fe-124">管理者は、保管ロックが適用された後に保持に関するポリシーを無効にしたり、削除したりすることができないため、この機能の有効化は、偶発的な構成を予防するものとして UI で使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a61fe-124">Because administrators can't disable or delete a policy for retention after this lock is applied, enabling this feature is not available in the UI to safeguard against accidental configuration.</span></span>

<span data-ttu-id="a61fe-125">すべての保持に関するポリシーおよびそのいかなる構成も、保管ロックをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a61fe-125">All policies for retention and with any configuration support Preservation Lock.</span></span>

1. <span data-ttu-id="a61fe-126">[セキュリティ/コンプライアンス センター PowerShell に接続します](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a61fe-126">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="a61fe-127">[Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy) を実行してロックするポリシーの名前を検索します。</span><span class="sxs-lookup"><span data-stu-id="a61fe-127">Find the name of the policy that you want to lock by running [Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy).</span></span> <span data-ttu-id="a61fe-128">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a61fe-128">For example:</span></span>
    
   ![PowerShell のアイテム保持ポリシーの一覧](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. <span data-ttu-id="a61fe-130">ポリシーに保管ロックを設定するには、ポリシーの名前を指定して [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) コマンドレットを実行し、*RestrictiveRetention* パラメーターを true に設定します。</span><span class="sxs-lookup"><span data-stu-id="a61fe-130">To place a Preservation Lock on your policy, run the [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet with the name of the policy, and the *RestrictiveRetention* parameter set to true:</span></span>
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    <span data-ttu-id="a61fe-131">例:</span><span class="sxs-lookup"><span data-stu-id="a61fe-131">For example:</span></span>
    
    ![PowerShell の RestrictiveRetention パラメーター](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     <span data-ttu-id="a61fe-133">メッセージが表示されたら、この構成に含まれる制限事項を読んで確認し、**Y** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a61fe-133">When prompted, read and acknowledge the restrictions that come with this configuration by entering **Y**:</span></span>
    
   ![PowerShell でアイテム保持ポリシーをロックすることを確認するプロンプト](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="a61fe-135">アイテム保持ポリシーに保管ロックが設定されました。</span><span class="sxs-lookup"><span data-stu-id="a61fe-135">A Preservation Lock is now placed on the policy.</span></span> <span data-ttu-id="a61fe-136">確認するには、`Get-RetentionCompliancePolicy` をもう一度実行しますが、ポリシーの名前を指定してポリシー パラメーターを表示します。</span><span class="sxs-lookup"><span data-stu-id="a61fe-136">To confirm, run `Get-RetentionCompliancePolicy` again, but specify the policy name and display the policy parameters:</span></span>

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

<span data-ttu-id="a61fe-137">**RestrictiveRetention** が **True** に設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a61fe-137">You should see **RestrictiveRetention** is set to **True**.</span></span> <span data-ttu-id="a61fe-138">例:</span><span class="sxs-lookup"><span data-stu-id="a61fe-138">For example:</span></span>

![PowerShell に表示されるすべてのパラメーターを含むロックされたポリシー](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a><span data-ttu-id="a61fe-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="a61fe-140">See also</span></span>

[<span data-ttu-id="a61fe-141">情報ガバナンスおよびレコード管理の規制要件を満たすために役立つリソース</span><span class="sxs-lookup"><span data-stu-id="a61fe-141">Resources to help you meet regulatory requirements for information governance and records management</span></span>](retention-regulatory-requirements.md)