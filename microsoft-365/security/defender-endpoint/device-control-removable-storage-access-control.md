---
title: Microsoft Defender for Endpoint Device Control リムーバブル 記憶域アクセス制御
description: Microsoft Defender for Endpoint の概要
keywords: リムーバブル 記憶域メディア
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 46ea74d11f9c54cd1d967058433a74ef4c1ead19
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300174"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="54c69-104">Microsoft Defender for Endpoint Device Control リムーバブル 記憶域アクセス制御</span><span class="sxs-lookup"><span data-stu-id="54c69-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="54c69-105">Microsoft Defender for Endpoint Device Control リムーバブル 記憶域アクセス制御を使用すると、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="54c69-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>
- <span data-ttu-id="54c69-106">除外の付いたリムーバブル 記憶域への読み取り、書き込み、または実行アクセスの監査、許可、または防止</span><span class="sxs-lookup"><span data-stu-id="54c69-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="54c69-107">特権</span><span class="sxs-lookup"><span data-stu-id="54c69-107">Privilege</span></span> |<span data-ttu-id="54c69-108">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="54c69-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="54c69-109">Access</span><span class="sxs-lookup"><span data-stu-id="54c69-109">Access</span></span>    |  <span data-ttu-id="54c69-110">読み取り、書き込み、実行</span><span class="sxs-lookup"><span data-stu-id="54c69-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="54c69-111">アクション モード</span><span class="sxs-lookup"><span data-stu-id="54c69-111">Action Mode</span></span>    |    <span data-ttu-id="54c69-112">監査、許可、防止</span><span class="sxs-lookup"><span data-stu-id="54c69-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="54c69-113">CSP サポート</span><span class="sxs-lookup"><span data-stu-id="54c69-113">CSP Support</span></span>   |   <span data-ttu-id="54c69-114">はい</span><span class="sxs-lookup"><span data-stu-id="54c69-114">Yes</span></span>      |
|<span data-ttu-id="54c69-115">GPO サポート</span><span class="sxs-lookup"><span data-stu-id="54c69-115">GPO Support</span></span>    |   <span data-ttu-id="54c69-116">はい</span><span class="sxs-lookup"><span data-stu-id="54c69-116">Yes</span></span>      |
|<span data-ttu-id="54c69-117">ユーザー ベースのサポート</span><span class="sxs-lookup"><span data-stu-id="54c69-117">User-based Support</span></span>     |   <span data-ttu-id="54c69-118">はい</span><span class="sxs-lookup"><span data-stu-id="54c69-118">Yes</span></span>      |
|<span data-ttu-id="54c69-119">コンピューター ベースのサポート</span><span class="sxs-lookup"><span data-stu-id="54c69-119">Machine-based Support</span></span>    |    <span data-ttu-id="54c69-120">はい</span><span class="sxs-lookup"><span data-stu-id="54c69-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="54c69-121">エンドポイントを準備する</span><span class="sxs-lookup"><span data-stu-id="54c69-121">Prepare your endpoints</span></span>

<span data-ttu-id="54c69-122">マルウェア対策クライアント バージョン **4.18.2103.3** 以降の Windows 10 デバイスにリムーバブル 記憶域アクセス制御を展開します。</span><span class="sxs-lookup"><span data-stu-id="54c69-122">Deploy Removable Storage Access Control on Windows 10 devices that have Anti-malware Client Version **4.18.2103.3 or later**.</span></span>
1. <span data-ttu-id="54c69-123">**4.18.2104** 以降: SerialNumberId の追加、VID_PIDパス ベースの GPO のサポート</span><span class="sxs-lookup"><span data-stu-id="54c69-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support</span></span>

2. <span data-ttu-id="54c69-124">**4.18.2105** 以降 : HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId のワイルドカード サポートの追加、特定のコンピューター上の特定のユーザーの組み合わせ、削除可能な SSD (SanDisk Extreme SSD)/USB Attached SCSI (UAS) のサポート</span><span class="sxs-lookup"><span data-stu-id="54c69-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

:::image type="content" source="images/powershell.png" alt-text="PowerShell インターフェイス":::

## <a name="policy-properties"></a><span data-ttu-id="54c69-126">ポリシーのプロパティ</span><span class="sxs-lookup"><span data-stu-id="54c69-126">Policy properties</span></span>

<span data-ttu-id="54c69-127">次のプロパティを使用して、リムーバブル 記憶域グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="54c69-127">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="54c69-128">**プロパティ名: グループ ID**</span><span class="sxs-lookup"><span data-stu-id="54c69-128">**Property name: Group ID**</span></span>

1. <span data-ttu-id="54c69-129">説明: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)、一意の ID は、グループを表し、ポリシーで使用されます。</span><span class="sxs-lookup"><span data-stu-id="54c69-129">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="54c69-130">**プロパティ名: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="54c69-130">**Property name: DescriptorIdList**</span></span>

1. <span data-ttu-id="54c69-131">説明: グループでカバーするデバイス プロパティを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="54c69-131">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="54c69-132">グループでカバーするデバイス のプロパティを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="54c69-132">List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="54c69-133">各デバイス プロパティの詳細については、上記 **の「デバイスのプロパティ** 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c69-133">For each device property, see **Device Properties** section above for more detail.</span></span>

1. <span data-ttu-id="54c69-134">オプション:</span><span class="sxs-lookup"><span data-stu-id="54c69-134">Options:</span></span>
    - <span data-ttu-id="54c69-135">プライマリ ID</span><span class="sxs-lookup"><span data-stu-id="54c69-135">Primary ID</span></span>
        - <span data-ttu-id="54c69-136">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="54c69-136">RemovableMediaDevices</span></span>
        - <span data-ttu-id="54c69-137">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="54c69-137">CdRomDevices</span></span>
    - <span data-ttu-id="54c69-138">DeviceId</span><span class="sxs-lookup"><span data-stu-id="54c69-138">DeviceId</span></span>
    - <span data-ttu-id="54c69-139">HardwareId</span><span class="sxs-lookup"><span data-stu-id="54c69-139">HardwareId</span></span>
    - <span data-ttu-id="54c69-140">InstancePathId</span><span class="sxs-lookup"><span data-stu-id="54c69-140">InstancePathId</span></span>
    - <span data-ttu-id="54c69-141">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="54c69-141">FriendlyNameId</span></span>
    - <span data-ttu-id="54c69-142">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="54c69-142">SerialNumberId</span></span>
    - <span data-ttu-id="54c69-143">VID</span><span class="sxs-lookup"><span data-stu-id="54c69-143">VID</span></span>
    - <span data-ttu-id="54c69-144">PID</span><span class="sxs-lookup"><span data-stu-id="54c69-144">PID</span></span>
    - <span data-ttu-id="54c69-145">VID_PID</span><span class="sxs-lookup"><span data-stu-id="54c69-145">VID_PID</span></span>
        - <span data-ttu-id="54c69-146">0751_55E0: この完全な VID/PID ペアと一致する</span><span class="sxs-lookup"><span data-stu-id="54c69-146">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="54c69-147">_55E0: PID=55E0 で任意のメディアを一致する</span><span class="sxs-lookup"><span data-stu-id="54c69-147">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="54c69-148">0751_: 任意のメディアを VID=0751 と一致する</span><span class="sxs-lookup"><span data-stu-id="54c69-148">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="54c69-149">**プロパティ名: MatchType**</span><span class="sxs-lookup"><span data-stu-id="54c69-149">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="54c69-150">説明: DescriptorIDList で複数のデバイス プロパティが使用されている場合、MatchType はリレーションシップを定義します。</span><span class="sxs-lookup"><span data-stu-id="54c69-150">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

1. <span data-ttu-id="54c69-151">オプション:</span><span class="sxs-lookup"><span data-stu-id="54c69-151">Options:</span></span>
    - <span data-ttu-id="54c69-152">MatchAll: DescriptorIdList の下の属性は **And** リレーションシップです。たとえば、管理者が DeviceID と InstancePathID を置く場合、接続されている USB ごとに、システムは USB が両方の値を満たするかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="54c69-152">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>

    - <span data-ttu-id="54c69-153">MatchAny: DescriptorIdList の下の属性は **Or リレーションシップ** です。たとえば、管理者が DeviceID と InstancePathID を置く場合、接続されている USB ごとに、USB が同じ **DeviceID** または **InstanceID** 値を持っている限り、システムは強制を実行します。</span><span class="sxs-lookup"><span data-stu-id="54c69-153">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="54c69-154">アクセス制御ポリシーのプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="54c69-154">Following are the access control policy properties:</span></span>

<span data-ttu-id="54c69-155">**プロパティ名: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="54c69-155">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="54c69-156">説明: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)、一意の ID はポリシーを表し、レポートとトラブルシューティングで使用されます。</span><span class="sxs-lookup"><span data-stu-id="54c69-156">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="54c69-157">**プロパティ名: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="54c69-157">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="54c69-158">説明: ポリシーが適用されるグループ。</span><span class="sxs-lookup"><span data-stu-id="54c69-158">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="54c69-159">複数のグループが追加されている場合、ポリシーは、すべてのグループ内の任意のメディアに適用されます。</span><span class="sxs-lookup"><span data-stu-id="54c69-159">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

1. <span data-ttu-id="54c69-160">オプション: このインスタンスでグループ ID/GUID を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c69-160">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="54c69-161">次の例は、GroupID の使用法を示しています。</span><span class="sxs-lookup"><span data-stu-id="54c69-161">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="54c69-162">**プロパティ名: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="54c69-162">**Property name: ExcludedIDList**</span></span>

1. <span data-ttu-id="54c69-163">説明: ポリシーが適用されないグループ。</span><span class="sxs-lookup"><span data-stu-id="54c69-163">Description: The group(s) that the policy will not be applied to.</span></span>
1. <span data-ttu-id="54c69-164">オプション: このインスタンスでグループ ID/GUID を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c69-164">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="54c69-165">**プロパティ名: エントリ ID**</span><span class="sxs-lookup"><span data-stu-id="54c69-165">**Property name: Entry ID**</span></span>

1. <span data-ttu-id="54c69-166">説明: 1 つの PolicyRule に複数のエントリを指定できます。一意の GUID を持つ各エントリは、デバイスコントロールに 1 つの制限を指示します。</span><span class="sxs-lookup"><span data-stu-id="54c69-166">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="54c69-167">**プロパティ名: Type**</span><span class="sxs-lookup"><span data-stu-id="54c69-167">**Property name: Type**</span></span>

1. <span data-ttu-id="54c69-168">説明: IncludedIDList のリムーバブル 記憶域グループのアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="54c69-168">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="54c69-169">適用: 許可または拒否</span><span class="sxs-lookup"><span data-stu-id="54c69-169">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="54c69-170">監査: AuditAllowed または AuditDenied</span><span class="sxs-lookup"><span data-stu-id="54c69-170">Audit: AuditAllowed or AuditDenied</span></span> 
1. <span data-ttu-id="54c69-171">オプション:</span><span class="sxs-lookup"><span data-stu-id="54c69-171">Options:</span></span>
    - <span data-ttu-id="54c69-172">許可</span><span class="sxs-lookup"><span data-stu-id="54c69-172">Allow</span></span>
    - <span data-ttu-id="54c69-173">拒否</span><span class="sxs-lookup"><span data-stu-id="54c69-173">Deny</span></span>
    - <span data-ttu-id="54c69-174">AuditAllowed: アクセスが許可されている場合の通知とイベントを定義します。</span><span class="sxs-lookup"><span data-stu-id="54c69-174">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="54c69-175">AuditDenied: アクセスが拒否された場合の通知とイベントを定義します。は、Deny エントリと共 **に動作する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="54c69-175">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="54c69-176">同じメディアに対して競合の種類がある場合、システムはポリシーの最初のメディアを適用します。</span><span class="sxs-lookup"><span data-stu-id="54c69-176">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="54c69-177">競合の種類の例として、[許可] と **[拒否]** **があります**。</span><span class="sxs-lookup"><span data-stu-id="54c69-177">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="54c69-178">**プロパティ名: オプション**</span><span class="sxs-lookup"><span data-stu-id="54c69-178">**Property name: Options**</span></span>

1. <span data-ttu-id="54c69-179">説明: 通知を表示するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="54c69-179">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="デバイスの状態を確認できる画面":::

1. <span data-ttu-id="54c69-181">オプション: 0 ~ 4。</span><span class="sxs-lookup"><span data-stu-id="54c69-181">Options: 0-4.</span></span> <span data-ttu-id="54c69-182">[許可] または [拒否] の種類が選択されている場合:</span><span class="sxs-lookup"><span data-stu-id="54c69-182">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="54c69-183">0: 何も</span><span class="sxs-lookup"><span data-stu-id="54c69-183">0: nothing</span></span>
   - <span data-ttu-id="54c69-184">4: この **エントリに対して AuditAllowed** と **AuditDenied を** 無効にします。</span><span class="sxs-lookup"><span data-stu-id="54c69-184">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="54c69-185">ブロックが **発生** し **、AuditDenied** が構成されている場合でも、システムは通知を表示されません。</span><span class="sxs-lookup"><span data-stu-id="54c69-185">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="54c69-186">Type **AuditAllowed または** **AuditDenied が** 選択されている場合:</span><span class="sxs-lookup"><span data-stu-id="54c69-186">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="54c69-187">0: 何も</span><span class="sxs-lookup"><span data-stu-id="54c69-187">0: nothing</span></span>
   - <span data-ttu-id="54c69-188">1: 通知を表示する</span><span class="sxs-lookup"><span data-stu-id="54c69-188">1: show notification</span></span>
   - <span data-ttu-id="54c69-189">2: 送信イベント</span><span class="sxs-lookup"><span data-stu-id="54c69-189">2: send event</span></span>
   - <span data-ttu-id="54c69-190">3: 通知を表示し、イベントを送信する</span><span class="sxs-lookup"><span data-stu-id="54c69-190">3: show notification and send event</span></span>

<span data-ttu-id="54c69-191">**プロパティ名: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="54c69-191">**Property name: AccessMask**</span></span>

1. <span data-ttu-id="54c69-192">説明: アクセスを定義します。</span><span class="sxs-lookup"><span data-stu-id="54c69-192">Description: Defines the access.</span></span>

1. <span data-ttu-id="54c69-193">オプション: 1 ~ 7:</span><span class="sxs-lookup"><span data-stu-id="54c69-193">Options: 1-7:</span></span>
    - <span data-ttu-id="54c69-194">1: 読み取り</span><span class="sxs-lookup"><span data-stu-id="54c69-194">1: Read</span></span>
    - <span data-ttu-id="54c69-195">2: 書き込み</span><span class="sxs-lookup"><span data-stu-id="54c69-195">2: Write</span></span>
    - <span data-ttu-id="54c69-196">3: 読み取りおよび書き込み</span><span class="sxs-lookup"><span data-stu-id="54c69-196">3: Read and Write</span></span>
    - <span data-ttu-id="54c69-197">4: 実行</span><span class="sxs-lookup"><span data-stu-id="54c69-197">4: Execute</span></span>
    - <span data-ttu-id="54c69-198">5: 読み取りおよび実行</span><span class="sxs-lookup"><span data-stu-id="54c69-198">5: Read and Execute</span></span>
    - <span data-ttu-id="54c69-199">6: 書き込みと実行</span><span class="sxs-lookup"><span data-stu-id="54c69-199">6: Write and Execute</span></span>
    - <span data-ttu-id="54c69-200">7: 読み取りおよび書き込みと実行</span><span class="sxs-lookup"><span data-stu-id="54c69-200">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="54c69-201">一般的なリムーバブル 記憶域アクセス制御のシナリオ</span><span class="sxs-lookup"><span data-stu-id="54c69-201">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="54c69-202">Microsoft Defender for Endpoint リムーバブル 記憶域アクセス制御について理解するために、一般的なシナリオをまとめました。</span><span class="sxs-lookup"><span data-stu-id="54c69-202">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="54c69-203">シナリオ 1: すべてのユーザーへの書き込みおよび実行アクセスを防止するが、特定の承認済み USB を許可する</span><span class="sxs-lookup"><span data-stu-id="54c69-203">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="54c69-204">グループを作成する</span><span class="sxs-lookup"><span data-stu-id="54c69-204">Create groups</span></span>
    1. <span data-ttu-id="54c69-205">グループ 1: リムーバブル 記憶域と CD/DVD。</span><span class="sxs-lookup"><span data-stu-id="54c69-205">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="54c69-206">リムーバブル 記憶域と CD/DVD の例は、グループ **9b28fae8-72f7-4267-a1a5-685f747a7146** のサンプルの Any Removable Storage および [CD-DVD Group.xmlファイル](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) です。</span><span class="sxs-lookup"><span data-stu-id="54c69-206">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="54c69-207">グループ 2: デバイスのプロパティに基づく承認済み USB。</span><span class="sxs-lookup"><span data-stu-id="54c69-207">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="54c69-208">この使用例の例は、サンプル承認済み [USB Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)ファイルのインスタンス ID – グループ **65fa649a-a111-4912-9294-fb6337a25038** です。</span><span class="sxs-lookup"><span data-stu-id="54c69-208">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="54c69-209">値に置き `&` 換 `&amp;` える必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c69-209">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="54c69-210">ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="54c69-210">Create policy</span></span>
    1. <span data-ttu-id="54c69-211">ポリシー 1: 書き込みおよび実行アクセスをブロックしますが、承認済みの USB を許可します。</span><span class="sxs-lookup"><span data-stu-id="54c69-211">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="54c69-212">この使用例の例は、シナリオ 1 ブロック書き込みおよび実行アクセスのサンプルの PolicyRule **c544a991-5786-4402-9402-a032cb790d0e** ですが、承認された [USB .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) ファイルを許可します。</span><span class="sxs-lookup"><span data-stu-id="54c69-212">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="54c69-213">ポリシー 2: 許可された USB への書き込みおよび実行アクセスを監査します。</span><span class="sxs-lookup"><span data-stu-id="54c69-213">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="54c69-214">この使用例の例として、PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** (シナリオ [1 監査](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 書き込みおよび承認済み USBs.xmlファイルへのアクセスの実行) があります。</span><span class="sxs-lookup"><span data-stu-id="54c69-214">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="54c69-215">シナリオ 2: 特定の承認されていない USB をブロックするを含むすべてのユーザーへの書き込みおよび実行アクセスを監査する</span><span class="sxs-lookup"><span data-stu-id="54c69-215">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="54c69-216">グループを作成する</span><span class="sxs-lookup"><span data-stu-id="54c69-216">Create groups</span></span>
    1. <span data-ttu-id="54c69-217">グループ 1: リムーバブル 記憶域と CD/DVD。</span><span class="sxs-lookup"><span data-stu-id="54c69-217">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="54c69-218">この使用例の例は、サンプル Any Removable Storage および [CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)ファイルのグループ **9b28fae8-72f7-4267-a1a5-685f747a7146** です。</span><span class="sxs-lookup"><span data-stu-id="54c69-218">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="54c69-219">グループ 2: サンプルの未承認の USB Group.xmlファイルのデバイス プロパティに基づく未承認 [の USB(](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)ベンダー ID/製品 ID、フレンドリー名 – グループ **65fa649a-a111-4912-9294-fb6337a25038** など)。</span><span class="sxs-lookup"><span data-stu-id="54c69-219">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="54c69-220">値に置き `&` 換 `&amp;` える必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c69-220">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="54c69-221">ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="54c69-221">Create policy</span></span>
    1. <span data-ttu-id="54c69-222">ポリシー 1: 特定の承認されていない USB をブロックする権限を持つすべてのユーザーに対する書き込みおよび実行アクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="54c69-222">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="54c69-223">この使用例の例として、PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** のサンプルシナリオ [2](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Audit Write and Execute access to all but block specific 未承認の USBs.xmlファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="54c69-223">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="54c69-224">ポリシー 2: 他のユーザーへの書き込みおよび実行アクセスを監査します。</span><span class="sxs-lookup"><span data-stu-id="54c69-224">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="54c69-225">この使用例の例は、「シナリオ [2](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Audit Write and Execute access to others.xmlfile」の PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** です。</span><span class="sxs-lookup"><span data-stu-id="54c69-225">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="54c69-226">グループ ポリシーによるポリシーの展開と管理</span><span class="sxs-lookup"><span data-stu-id="54c69-226">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="54c69-227">リムーバブル 記憶域アクセス制御機能を使用すると、グループ ポリシーを使用してユーザーまたはデバイス、または両方にポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="54c69-227">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="54c69-228">ライセンス</span><span class="sxs-lookup"><span data-stu-id="54c69-228">Licensing</span></span>

<span data-ttu-id="54c69-229">リムーバブル 記憶域アクセス制御を開始する前に [、Microsoft 365 サブスクリプションを確認する必要があります](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。</span><span class="sxs-lookup"><span data-stu-id="54c69-229">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="54c69-230">リムーバブル 記憶域アクセス制御にアクセスして使用するには、Microsoft 365 E5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="54c69-230">To access and use Removable Storage Access Control, you must have Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="54c69-231">グループ ポリシーによるポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="54c69-231">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="54c69-232">すべてのグループを 1 つの `<Groups>` `</Groups>` xml ファイルに結合します。</span><span class="sxs-lookup"><span data-stu-id="54c69-232">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="54c69-233">次の図は、シナリオ 1: 書き込みおよび実行アクセスを許可するが、特定の承認済み USB を許可するの例 [を示しています](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)。</span><span class="sxs-lookup"><span data-stu-id="54c69-233">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="デバイスで特定の承認済み USB を許可する構成設定を表示する画面":::
    
2. <span data-ttu-id="54c69-235">すべてのルールを 1 つの `<PolicyRules>` `</PolicyRules>` xml ファイルに結合します。</span><span class="sxs-lookup"><span data-stu-id="54c69-235">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="54c69-236">特定のユーザーを制限する場合は、エントリに SID プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="54c69-236">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="54c69-237">ポリシー Entry に SID がない場合、エントリはコンピューターのすべてのログイン インスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="54c69-237">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="54c69-238">次の図は、SID プロパティの使用法を示しています。シナリオ [1:](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)書き込みおよび実行のアクセスをすべて防ぐが、特定の承認済み USB を許可する例を示します。</span><span class="sxs-lookup"><span data-stu-id="54c69-238">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="SID プロパティ属性の使用法を示すコードを表示する画面":::

3. <span data-ttu-id="54c69-240">ルールとグループ XML ファイルの両方をネットワーク共有フォルダーに保存し、ネットワーク共有フォルダー パスを [グループ ポリシー] 設定に格納します。[コンピューターの構成] -> [管理用テンプレート] -> Windows コンポーネント **-> Microsoft Defender Antivirus -> Device Control: 'Define** device control policy groups' and 'Define device control policy rules' 。</span><span class="sxs-lookup"><span data-stu-id="54c69-240">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="54c69-241">ポリシーを持つには、ターゲット コンピューターがネットワーク共有にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c69-241">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="54c69-242">ただし、ポリシーを読み取った後は、コンピューターの再起動後も、ネットワーク共有接続は不要になります。</span><span class="sxs-lookup"><span data-stu-id="54c69-242">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="[デバイス制御] 画面":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="54c69-244">Intune OMA-URI によるポリシーの展開と管理</span><span class="sxs-lookup"><span data-stu-id="54c69-244">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="54c69-245">リムーバブル 記憶域アクセス制御機能を使用すると、OMA-URI を介してユーザーまたはデバイス、または両方にポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="54c69-245">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="54c69-246">ライセンス</span><span class="sxs-lookup"><span data-stu-id="54c69-246">Licensing</span></span>

<span data-ttu-id="54c69-247">リムーバブル 記憶域アクセス制御を開始する前に [、Microsoft 365 サブスクリプションを確認する必要があります](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。</span><span class="sxs-lookup"><span data-stu-id="54c69-247">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="54c69-248">リムーバブル 記憶域アクセス制御にアクセスして使用するには、Microsoft 365 E3 が必要です。</span><span class="sxs-lookup"><span data-stu-id="54c69-248">To access and use Removable Storage Access Control, you must have Microsoft 365 E3.</span></span>

### <a name="permission"></a><span data-ttu-id="54c69-249">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="54c69-249">Permission</span></span>

<span data-ttu-id="54c69-250">Intune でのポリシーの展開では、デバイス構成プロファイルを作成、編集、更新、または削除するためのアクセス許可がアカウントに必要です。</span><span class="sxs-lookup"><span data-stu-id="54c69-250">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="54c69-251">カスタム ロールを作成するか、これらのアクセス許可を持つ組み込みロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="54c69-251">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="54c69-252">ポリシーとプロファイル マネージャーの役割</span><span class="sxs-lookup"><span data-stu-id="54c69-252">Policy and profile Manager role</span></span>
- <span data-ttu-id="54c69-253">デバイス構成プロファイルに対してレポートの作成/編集/更新/読み取り/削除/表示権限を有効にしたカスタム ロール</span><span class="sxs-lookup"><span data-stu-id="54c69-253">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="54c69-254">全体管理者</span><span class="sxs-lookup"><span data-stu-id="54c69-254">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="54c69-255">OMA-URI によるポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="54c69-255">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="54c69-256">**Microsoft Endpoint Manager 管理センター ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 以降 & プロファイル: Custom**</span><span class="sxs-lookup"><span data-stu-id="54c69-256">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="54c69-257">グループごとに、OMA-URI ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="54c69-257">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="54c69-258">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="54c69-258">OMA-URI:</span></span>

      <span data-ttu-id="54c69-259">/Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="54c69-259">/Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="54c69-260">たとえば、サンプル **内のリムーバブル 記憶域と CD/DVD** グループの場合、リンクは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="54c69-260">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="54c69-261">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="54c69-261">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="54c69-262">データ型: 文字列 (XML ファイル)</span><span class="sxs-lookup"><span data-stu-id="54c69-262">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="STRING データ型の xml ファイル":::

2. <span data-ttu-id="54c69-264">ポリシーごとに、OMA-URI も作成します。</span><span class="sxs-lookup"><span data-stu-id="54c69-264">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="54c69-265">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="54c69-265">OMA-URI:</span></span>

      <span data-ttu-id="54c69-266">/Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="54c69-266">/Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="54c69-267">たとえば、ブロック書き込みおよび実行アクセスの場合、サンプルで承認 **された USB** ルールを許可するには、次のリンクが必要です。</span><span class="sxs-lookup"><span data-stu-id="54c69-267">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="54c69-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData。</span><span class="sxs-lookup"><span data-stu-id="54c69-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="54c69-269">データ型: 文字列 (XML ファイル)</span><span class="sxs-lookup"><span data-stu-id="54c69-269">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" alt-text="STRING データ型の XML ファイルの表示":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="54c69-271">Intune ユーザー インターフェイスを使用したポリシーの展開と管理</span><span class="sxs-lookup"><span data-stu-id="54c69-271">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="54c69-272">この機能はまだ使用できません。</span><span class="sxs-lookup"><span data-stu-id="54c69-272">This capability is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="54c69-273">Microsoft Defender for Endpoint でデバイスコントロールリムーバブル 記憶域アクセス制御データを表示する</span><span class="sxs-lookup"><span data-stu-id="54c69-273">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="54c69-274">Microsoft 365 セキュリティ ポータルには、Device Control リムーバブル 記憶域アクセス制御によってブロックされたリムーバブル 記憶域が表示されます。</span><span class="sxs-lookup"><span data-stu-id="54c69-274">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="54c69-275">Microsoft 365 セキュリティにアクセスするには、次のサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="54c69-275">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="54c69-276">Microsoft 365 for E5 レポート</span><span class="sxs-lookup"><span data-stu-id="54c69-276">Microsoft 365 for E5 reporting</span></span>

```
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot; 
| extend parsed=parse_json(AdditionalFields) 
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)  
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)  
| extend MediaBusType = tostring(parsed.BusType)  
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId) 
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaName = tostring(parsed.MediaName) 
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)  
| extend MediaProductId = tostring(parsed.ProductId)  
| extend MediaVendorId = tostring(parsed.VendorId)  
| extend MediaSerialNumber = tostring(parsed.SerialNumber)  
| extend MediaVolume = tostring(parsed.Volume)  
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume 
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="リムーバブル 記憶域のブロックを示す画面":::
