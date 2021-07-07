---
title: Microsoft Defender for Endpoint Device Control リムーバブル Storage アクセス制御
description: Microsoft Defender for Endpoint の概要
keywords: リムーバブル 記憶域メディア
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0b0f7c5a4a75fdc80509dbc02a43d28f7c93fd7c
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327049"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="96547-104">Microsoft Defender for Endpoint Device Control リムーバブル Storage アクセス制御</span><span class="sxs-lookup"><span data-stu-id="96547-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="96547-105">Microsoft Defender for Endpoint Device Control リムーバブル Storageアクセス制御を使用すると、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="96547-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>

- <span data-ttu-id="96547-106">除外の付いたリムーバブル 記憶域への読み取り、書き込み、または実行アクセスの監査、許可、または防止</span><span class="sxs-lookup"><span data-stu-id="96547-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="96547-107">特権</span><span class="sxs-lookup"><span data-stu-id="96547-107">Privilege</span></span> |<span data-ttu-id="96547-108">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="96547-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="96547-109">Access</span><span class="sxs-lookup"><span data-stu-id="96547-109">Access</span></span>    |  <span data-ttu-id="96547-110">読み取り、書き込み、実行</span><span class="sxs-lookup"><span data-stu-id="96547-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="96547-111">アクション モード</span><span class="sxs-lookup"><span data-stu-id="96547-111">Action Mode</span></span>    |    <span data-ttu-id="96547-112">監査、許可、防止</span><span class="sxs-lookup"><span data-stu-id="96547-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="96547-113">CSP サポート</span><span class="sxs-lookup"><span data-stu-id="96547-113">CSP Support</span></span>   |   <span data-ttu-id="96547-114">はい</span><span class="sxs-lookup"><span data-stu-id="96547-114">Yes</span></span>      |
|<span data-ttu-id="96547-115">GPO サポート</span><span class="sxs-lookup"><span data-stu-id="96547-115">GPO Support</span></span>    |   <span data-ttu-id="96547-116">はい</span><span class="sxs-lookup"><span data-stu-id="96547-116">Yes</span></span>      |
|<span data-ttu-id="96547-117">ユーザー ベースのサポート</span><span class="sxs-lookup"><span data-stu-id="96547-117">User-based Support</span></span>     |   <span data-ttu-id="96547-118">はい</span><span class="sxs-lookup"><span data-stu-id="96547-118">Yes</span></span>      |
|<span data-ttu-id="96547-119">コンピューター ベースのサポート</span><span class="sxs-lookup"><span data-stu-id="96547-119">Machine-based Support</span></span>    |    <span data-ttu-id="96547-120">はい</span><span class="sxs-lookup"><span data-stu-id="96547-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="96547-121">エンドポイントを準備する</span><span class="sxs-lookup"><span data-stu-id="96547-121">Prepare your endpoints</span></span>

<span data-ttu-id="96547-122">マルウェア対策クライアント Storage **4.18.2103.3** 以降の Windows 10 デバイスにリムーバブル アクセス制御を展開します。</span><span class="sxs-lookup"><span data-stu-id="96547-122">Deploy Removable Storage Access Control on Windows 10 devices that have antimalware client version **4.18.2103.3 or later**.</span></span>

- <span data-ttu-id="96547-123">**4.18.2104** 以降: SerialNumberId の追加、VID_PID、ファイルパス ベースの GPO のサポート、ComputerSid</span><span class="sxs-lookup"><span data-stu-id="96547-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid</span></span>

- <span data-ttu-id="96547-124">**4.18.2105** 以降 : HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId のワイルドカード サポートの追加、特定のコンピューター上の特定のユーザーの組み合わせ、削除可能な SSD (SanDisk Extreme SSD)/USB Attached SCSI (UAS) のサポート</span><span class="sxs-lookup"><span data-stu-id="96547-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

- <span data-ttu-id="96547-125">**4.18.2107** 以降 : ポータブル Windows (WPD) のサポートを追加する (タブレットなどのモバイル デバイスの場合)</span><span class="sxs-lookup"><span data-stu-id="96547-125">**4.18.2107 or later**: Add Windows Portable Device (WPD) support (for mobile devices, such as tablets)</span></span>

:::image type="content" source="images/powershell.png" alt-text="PowerShell インターフェイス":::

> [!NOTE]
> <span data-ttu-id="96547-127">どのコンポーネントWindows セキュリティアクティブである必要もありません。リムーバブル アクセス制御は、Storage状態とはWindows セキュリティできます。</span><span class="sxs-lookup"><span data-stu-id="96547-127">None of Windows Security components need to be active, you can run Removable Storage Access Control independent of Windows Security status.</span></span>

## <a name="policy-properties"></a><span data-ttu-id="96547-128">ポリシーのプロパティ</span><span class="sxs-lookup"><span data-stu-id="96547-128">Policy properties</span></span>

<span data-ttu-id="96547-129">次のプロパティを使用して、リムーバブル 記憶域グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="96547-129">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="96547-130">**プロパティ名: グループ ID**</span><span class="sxs-lookup"><span data-stu-id="96547-130">**Property name: Group Id**</span></span>

1. <span data-ttu-id="96547-131">説明: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)、一意の ID は、グループを表し、ポリシーで使用されます。</span><span class="sxs-lookup"><span data-stu-id="96547-131">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="96547-132">**プロパティ名: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="96547-132">**Property name: DescriptorIdList**</span></span>

2. <span data-ttu-id="96547-133">説明: グループでカバーするデバイス プロパティを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="96547-133">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="96547-134">各デバイス プロパティの詳細については、上記 **の「デバイスのプロパティ** 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96547-134">For each device property, see **Device Properties** section above for more detail.</span></span>

3. <span data-ttu-id="96547-135">オプション:</span><span class="sxs-lookup"><span data-stu-id="96547-135">Options:</span></span>
    - <span data-ttu-id="96547-136">PrimaryId</span><span class="sxs-lookup"><span data-stu-id="96547-136">PrimaryId</span></span>
        - <span data-ttu-id="96547-137">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="96547-137">RemovableMediaDevices</span></span>
        - <span data-ttu-id="96547-138">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="96547-138">CdRomDevices</span></span>
        - <span data-ttu-id="96547-139">WpdDevices</span><span class="sxs-lookup"><span data-stu-id="96547-139">WpdDevices</span></span>
    - <span data-ttu-id="96547-140">DeviceId</span><span class="sxs-lookup"><span data-stu-id="96547-140">DeviceId</span></span>
    - <span data-ttu-id="96547-141">HardwareId</span><span class="sxs-lookup"><span data-stu-id="96547-141">HardwareId</span></span>
    - <span data-ttu-id="96547-142">InstancePathId: InstancePathId は、システム内のデバイスを一意に識別する文字列です (たとえば、USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0)。</span><span class="sxs-lookup"><span data-stu-id="96547-142">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="96547-143">末尾の番号 (たとえば、&**0)** は使用可能なスロットを表し、デバイス間で変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="96547-143">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="96547-144">最適な結果を得る場合は、末尾にワイルドカードを使用します。</span><span class="sxs-lookup"><span data-stu-id="96547-144">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="96547-145">たとえば、USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="96547-145">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="96547-146">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="96547-146">FriendlyNameId</span></span>
    - <span data-ttu-id="96547-147">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="96547-147">SerialNumberId</span></span>
    - <span data-ttu-id="96547-148">VID</span><span class="sxs-lookup"><span data-stu-id="96547-148">VID</span></span>
    - <span data-ttu-id="96547-149">PID</span><span class="sxs-lookup"><span data-stu-id="96547-149">PID</span></span>
    - <span data-ttu-id="96547-150">VID_PID</span><span class="sxs-lookup"><span data-stu-id="96547-150">VID_PID</span></span>
        - <span data-ttu-id="96547-151">0751_55E0: この完全な VID/PID ペアと一致する</span><span class="sxs-lookup"><span data-stu-id="96547-151">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="96547-152">_55E0: PID=55E0 で任意のメディアを一致する</span><span class="sxs-lookup"><span data-stu-id="96547-152">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="96547-153">0751_: 任意のメディアを VID=0751 と一致する</span><span class="sxs-lookup"><span data-stu-id="96547-153">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="96547-154">**プロパティ名: MatchType**</span><span class="sxs-lookup"><span data-stu-id="96547-154">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="96547-155">説明: DescriptorIDList で複数のデバイス プロパティが使用されている場合、MatchType はリレーションシップを定義します。</span><span class="sxs-lookup"><span data-stu-id="96547-155">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

2. <span data-ttu-id="96547-156">オプション:</span><span class="sxs-lookup"><span data-stu-id="96547-156">Options:</span></span>

    - <span data-ttu-id="96547-157">MatchAll: DescriptorIdList の下の属性は **And** リレーションシップです。たとえば、管理者が DeviceID と InstancePathID を置く場合、接続されている USB ごとに、システムは USB が両方の値を満たするかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="96547-157">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>
    - <span data-ttu-id="96547-158">MatchAny: DescriptorIdList の下の属性は **Or リレーションシップ** です。たとえば、管理者が DeviceID と InstancePathID を置く場合、接続されている USB ごとに、USB が同じ **DeviceID** または **InstanceID** 値を持っている限り、システムは強制を実行します。</span><span class="sxs-lookup"><span data-stu-id="96547-158">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="96547-159">アクセス制御ポリシーのプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="96547-159">Following are the access control policy properties:</span></span>

<span data-ttu-id="96547-160">**プロパティ名: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="96547-160">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="96547-161">説明: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)、一意の ID はポリシーを表し、レポートとトラブルシューティングで使用されます。</span><span class="sxs-lookup"><span data-stu-id="96547-161">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="96547-162">**プロパティ名: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="96547-162">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="96547-163">説明: ポリシーが適用されるグループ。</span><span class="sxs-lookup"><span data-stu-id="96547-163">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="96547-164">複数のグループが追加されている場合、ポリシーは、すべてのグループ内の任意のメディアに適用されます。</span><span class="sxs-lookup"><span data-stu-id="96547-164">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

2. <span data-ttu-id="96547-165">オプション: このインスタンスでグループ ID/GUID を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96547-165">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="96547-166">次の例は、GroupID の使用法を示しています。</span><span class="sxs-lookup"><span data-stu-id="96547-166">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="96547-167">**プロパティ名: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="96547-167">**Property name: ExcludedIDList**</span></span>

<span data-ttu-id="96547-168">説明: ポリシーが適用されないグループ。</span><span class="sxs-lookup"><span data-stu-id="96547-168">Description: The group(s) that the policy will not be applied to.</span></span>

<span data-ttu-id="96547-169">オプション: このインスタンスでグループ ID/GUID を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96547-169">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="96547-170">**プロパティ名: エントリ ID**</span><span class="sxs-lookup"><span data-stu-id="96547-170">**Property name: Entry Id**</span></span>

1. <span data-ttu-id="96547-171">説明: 1 つの PolicyRule に複数のエントリを指定できます。一意の GUID を持つ各エントリは、デバイスコントロールに 1 つの制限を指示します。</span><span class="sxs-lookup"><span data-stu-id="96547-171">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="96547-172">**プロパティ名: Type**</span><span class="sxs-lookup"><span data-stu-id="96547-172">**Property name: Type**</span></span>

1. <span data-ttu-id="96547-173">説明: IncludedIDList のリムーバブル 記憶域グループのアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="96547-173">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="96547-174">適用: 許可または拒否</span><span class="sxs-lookup"><span data-stu-id="96547-174">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="96547-175">監査: AuditAllowed または AuditDenied</span><span class="sxs-lookup"><span data-stu-id="96547-175">Audit: AuditAllowed or AuditDenied</span></span> 

2. <span data-ttu-id="96547-176">オプション:</span><span class="sxs-lookup"><span data-stu-id="96547-176">Options:</span></span>

    - <span data-ttu-id="96547-177">許可</span><span class="sxs-lookup"><span data-stu-id="96547-177">Allow</span></span>
    - <span data-ttu-id="96547-178">拒否</span><span class="sxs-lookup"><span data-stu-id="96547-178">Deny</span></span>
    - <span data-ttu-id="96547-179">AuditAllowed: アクセスが許可されている場合の通知とイベントを定義します。</span><span class="sxs-lookup"><span data-stu-id="96547-179">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="96547-180">AuditDenied: アクセスが拒否された場合の通知とイベントを定義します。は、Deny エントリと共 **に動作する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="96547-180">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="96547-181">同じメディアに対して競合の種類がある場合、システムはポリシーの最初のメディアを適用します。</span><span class="sxs-lookup"><span data-stu-id="96547-181">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="96547-182">競合の種類の例として、[許可] と **[拒否]** **があります**。</span><span class="sxs-lookup"><span data-stu-id="96547-182">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="96547-183">**プロパティ名: Sid**</span><span class="sxs-lookup"><span data-stu-id="96547-183">**Property name: Sid**</span></span>

<span data-ttu-id="96547-184">説明: ローカル コンピューター Sid または AD オブジェクトの Sid は、このポリシーを特定のユーザー またはユーザー グループに適用するかどうかを定義します。1 つのエントリには最大 1 つの Sid を含め、Sid を使用しないエントリは、コンピューター上にポリシーを適用する方法を意味します。</span><span class="sxs-lookup"><span data-stu-id="96547-184">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific user or user group; one entry can have a maximum of one Sid and an entry without any Sid means applying the policy over the machine.</span></span>

<span data-ttu-id="96547-185">**プロパティ名: ComputerSid**</span><span class="sxs-lookup"><span data-stu-id="96547-185">**Property name: ComputerSid**</span></span>

<span data-ttu-id="96547-186">説明: ローカル コンピューター Sid または AD オブジェクトの Sid は、このポリシーを特定のコンピューターまたはコンピューター グループに適用するかどうかを定義します。1 つのエントリには最大 1 つの ComputerSid を指定し、ComputerSid を使用しないエントリはコンピューター上にポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="96547-186">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific machine or machine group; one entry can have a maximum of one ComputerSid and an entry without any ComputerSid means applying the policy over the machine.</span></span> <span data-ttu-id="96547-187">特定のユーザーと特定のコンピューターにエントリを適用する場合は、Sid と ComputerSid の両方を同じエントリに追加します。</span><span class="sxs-lookup"><span data-stu-id="96547-187">If you want to apply an Entry to a specific user and specific machine, add both Sid and ComputerSid into the same Entry.</span></span>

<span data-ttu-id="96547-188">**プロパティ名: オプション**</span><span class="sxs-lookup"><span data-stu-id="96547-188">**Property name: Options**</span></span>

<span data-ttu-id="96547-189">説明: 通知を表示するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="96547-189">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="デバイスの状態を確認できる画面":::

<span data-ttu-id="96547-191">オプション: 0 ~ 4。</span><span class="sxs-lookup"><span data-stu-id="96547-191">Options: 0-4.</span></span> <span data-ttu-id="96547-192">[許可] または [拒否] の種類が選択されている場合:</span><span class="sxs-lookup"><span data-stu-id="96547-192">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="96547-193">0: 何も</span><span class="sxs-lookup"><span data-stu-id="96547-193">0: nothing</span></span>
   - <span data-ttu-id="96547-194">4: この **エントリに対して AuditAllowed** と **AuditDenied を** 無効にします。</span><span class="sxs-lookup"><span data-stu-id="96547-194">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="96547-195">ブロックが **発生** し **、AuditDenied** が構成されている場合でも、システムは通知を表示されません。</span><span class="sxs-lookup"><span data-stu-id="96547-195">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="96547-196">Type **AuditAllowed または** **AuditDenied が** 選択されている場合:</span><span class="sxs-lookup"><span data-stu-id="96547-196">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="96547-197">0: 何も</span><span class="sxs-lookup"><span data-stu-id="96547-197">0: nothing</span></span>
   - <span data-ttu-id="96547-198">1: 通知を表示する</span><span class="sxs-lookup"><span data-stu-id="96547-198">1: show notification</span></span>
   - <span data-ttu-id="96547-199">2: 送信イベント</span><span class="sxs-lookup"><span data-stu-id="96547-199">2: send event</span></span>
   - <span data-ttu-id="96547-200">3: 通知を表示し、イベントを送信する</span><span class="sxs-lookup"><span data-stu-id="96547-200">3: show notification and send event</span></span>

<span data-ttu-id="96547-201">**プロパティ名: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="96547-201">**Property name: AccessMask**</span></span>

<span data-ttu-id="96547-202">説明: アクセスを定義します。</span><span class="sxs-lookup"><span data-stu-id="96547-202">Description: Defines the access.</span></span>

<span data-ttu-id="96547-203">オプション 1 ~ 7:</span><span class="sxs-lookup"><span data-stu-id="96547-203">Options 1-7:</span></span>
  - <span data-ttu-id="96547-204">1: 読み取り</span><span class="sxs-lookup"><span data-stu-id="96547-204">1: Read</span></span>
  - <span data-ttu-id="96547-205">2: 書き込み</span><span class="sxs-lookup"><span data-stu-id="96547-205">2: Write</span></span>
  - <span data-ttu-id="96547-206">3: 読み取りおよび書き込み</span><span class="sxs-lookup"><span data-stu-id="96547-206">3: Read and Write</span></span>
  - <span data-ttu-id="96547-207">4: 実行</span><span class="sxs-lookup"><span data-stu-id="96547-207">4: Execute</span></span>
  - <span data-ttu-id="96547-208">5: 読み取りおよび実行</span><span class="sxs-lookup"><span data-stu-id="96547-208">5: Read and Execute</span></span>
  - <span data-ttu-id="96547-209">6: 書き込みと実行</span><span class="sxs-lookup"><span data-stu-id="96547-209">6: Write and Execute</span></span>
  - <span data-ttu-id="96547-210">7: 読み取りおよび書き込みと実行</span><span class="sxs-lookup"><span data-stu-id="96547-210">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="96547-211">一般的なリムーバブル Storage アクセス制御のシナリオ</span><span class="sxs-lookup"><span data-stu-id="96547-211">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="96547-212">Microsoft Defender for Endpoint Removable Storageアクセス制御について理解するために、一般的なシナリオをまとめました。</span><span class="sxs-lookup"><span data-stu-id="96547-212">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="96547-213">シナリオ 1: すべてのユーザーへの書き込みおよび実行アクセスを防止するが、特定の承認済み USB を許可する</span><span class="sxs-lookup"><span data-stu-id="96547-213">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="96547-214">グループを作成する</span><span class="sxs-lookup"><span data-stu-id="96547-214">Create groups</span></span>

    1. <span data-ttu-id="96547-215">グループ 1: リムーバブル 記憶域と CD/DVD。</span><span class="sxs-lookup"><span data-stu-id="96547-215">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="96547-216">リムーバブル ストレージと CD/DVD の例として、グループ **9b28fae8-72f7-4267-a1a5-685f747a7146** のサンプル (Any Removable Storage および [CD-DVD Group.xmlファイル](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)) があります。</span><span class="sxs-lookup"><span data-stu-id="96547-216">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="96547-217">グループ 2: デバイスのプロパティに基づく承認済み USB。</span><span class="sxs-lookup"><span data-stu-id="96547-217">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="96547-218">この使用例の例は、サンプル承認済み [USB Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)ファイルのインスタンス ID – グループ **65fa649a-a111-4912-9294-fb6337a25038** です。</span><span class="sxs-lookup"><span data-stu-id="96547-218">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="96547-219">値に置き `&` 換 `&amp;` える必要があります。</span><span class="sxs-lookup"><span data-stu-id="96547-219">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="96547-220">ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="96547-220">Create policy</span></span>

    1. <span data-ttu-id="96547-221">ポリシー 1: 書き込みおよび実行アクセスをブロックしますが、承認済みの USB を許可します。</span><span class="sxs-lookup"><span data-stu-id="96547-221">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="96547-222">この使用例の例は、シナリオ [1](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)ブロック書き込みおよび実行アクセスのサンプルの PolicyRule **c544a991-5786-4402-9402-a032cb790d0e** ですが、承認された USBs.xmlファイルを許可します。</span><span class="sxs-lookup"><span data-stu-id="96547-222">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="96547-223">ポリシー 2: 許可された USB への書き込みおよび実行アクセスを監査します。</span><span class="sxs-lookup"><span data-stu-id="96547-223">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="96547-224">この使用例の例として、PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** (シナリオ [1 監査](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 書き込みおよび承認済み USBs.xmlファイルへのアクセスの実行) があります。</span><span class="sxs-lookup"><span data-stu-id="96547-224">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="96547-225">シナリオ 2: 特定の承認されていない USB をブロックするを含むすべてのユーザーへの書き込みおよび実行アクセスを監査する</span><span class="sxs-lookup"><span data-stu-id="96547-225">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="96547-226">グループを作成する</span><span class="sxs-lookup"><span data-stu-id="96547-226">Create groups</span></span>

    1. <span data-ttu-id="96547-227">グループ 1: リムーバブル 記憶域と CD/DVD。</span><span class="sxs-lookup"><span data-stu-id="96547-227">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="96547-228">この使用例の例は、サンプル Any Removable Storage および [CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)ファイルのグループ **9b28fae8-72f7-4267-a1a5-685f747a7146** です。</span><span class="sxs-lookup"><span data-stu-id="96547-228">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="96547-229">グループ 2: サンプルの未承認の USB Group.xmlファイルのデバイス プロパティに基づく未承認 [の USB(](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)ベンダー ID/製品 ID、フレンドリー名 – グループ **65fa649a-a111-4912-9294-fb6337a25038** など)。</span><span class="sxs-lookup"><span data-stu-id="96547-229">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="96547-230">値に置き `&` 換 `&amp;` える必要があります。</span><span class="sxs-lookup"><span data-stu-id="96547-230">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="96547-231">ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="96547-231">Create policy</span></span>

    1. <span data-ttu-id="96547-232">ポリシー 1: 特定の承認されていない USB をブロックする権限を持つすべてのユーザーに対する書き込みおよび実行アクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="96547-232">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="96547-233">この使用例の例として、PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** のサンプルシナリオ [2](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Audit Write and Execute access to all but block specific 未承認の USBs.xmlファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="96547-233">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="96547-234">ポリシー 2: 他のユーザーへの書き込みおよび実行アクセスを監査します。</span><span class="sxs-lookup"><span data-stu-id="96547-234">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="96547-235">この使用例の例は、「シナリオ [2](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Audit Write and Execute access to others.xmlfile」の PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** です。</span><span class="sxs-lookup"><span data-stu-id="96547-235">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="96547-236">グループ ポリシーによるポリシーの展開と管理</span><span class="sxs-lookup"><span data-stu-id="96547-236">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="96547-237">リムーバブル アクセスStorage機能を使用すると、グループ ポリシー経由でユーザーまたはデバイス、または両方にポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="96547-237">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="96547-238">ライセンス</span><span class="sxs-lookup"><span data-stu-id="96547-238">Licensing</span></span>

<span data-ttu-id="96547-239">リムーバブル アクセス制御の使用を開始するStorage、サブスクリプションを確認 [するMicrosoft 365があります](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。</span><span class="sxs-lookup"><span data-stu-id="96547-239">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="96547-240">リムーバブル アクセス制御にアクセスして使用Storageするには、リムーバブル アクセスコントロールまたはMicrosoft 365 E3必要Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="96547-240">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="96547-241">グループ ポリシーによるポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="96547-241">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="96547-242">すべてのグループを 1 つの `<Groups>` `</Groups>` xml ファイルに結合します。</span><span class="sxs-lookup"><span data-stu-id="96547-242">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="96547-243">次の図は、シナリオ 1: 書き込みおよび実行アクセスを許可するが、特定の承認済み USB を許可するの例 [を示しています](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)。</span><span class="sxs-lookup"><span data-stu-id="96547-243">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="デバイスで特定の承認済み USB を許可する構成設定を表示する画面":::
    
2. <span data-ttu-id="96547-245">すべてのルールを 1 つの `<PolicyRules>` `</PolicyRules>` xml ファイルに結合します。</span><span class="sxs-lookup"><span data-stu-id="96547-245">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="96547-246">特定のユーザーを制限する場合は、エントリに SID プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="96547-246">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="96547-247">ポリシー Entry に SID がない場合、エントリはコンピューターのすべてのログイン インスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="96547-247">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="96547-248">次の図は、SID プロパティの使用法を示しています。シナリオ [1:](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)書き込みおよび実行のアクセスをすべて防ぐが、特定の承認済み USB を許可する例を示します。</span><span class="sxs-lookup"><span data-stu-id="96547-248">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="SID プロパティ属性の使用法を示すコードを表示する画面":::

3. <span data-ttu-id="96547-250">ルールとグループ XML ファイルの両方をネットワーク共有フォルダーに保存し、ネットワーク共有フォルダー パスを [グループ ポリシー] 設定に格納します。[コンピューターの構成] -> [管理用テンプレート] -> Windows コンポーネント **-> Microsoft Defender ウイルス対策 ->** Device Control: 'デバイス コントロール ポリシー グループの定義' と [デバイス制御ポリシー ルールの定義] です。</span><span class="sxs-lookup"><span data-stu-id="96547-250">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="96547-251">ポリシーを持つには、ターゲット コンピューターがネットワーク共有にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="96547-251">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="96547-252">ただし、ポリシーを読み取った後は、コンピューターの再起動後も、ネットワーク共有接続は不要になります。</span><span class="sxs-lookup"><span data-stu-id="96547-252">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="[デバイス制御] 画面":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="96547-254">Intune OMA-URI によるポリシーの展開と管理</span><span class="sxs-lookup"><span data-stu-id="96547-254">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="96547-255">リムーバブル アクセスStorage機能を使用すると、OMA-URI を介してユーザーまたはデバイス、または両方にポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="96547-255">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="96547-256">ライセンス</span><span class="sxs-lookup"><span data-stu-id="96547-256">Licensing</span></span>

<span data-ttu-id="96547-257">リムーバブル アクセス制御の使用を開始するStorage、サブスクリプションを確認 [するMicrosoft 365があります](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。</span><span class="sxs-lookup"><span data-stu-id="96547-257">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="96547-258">リムーバブル アクセス制御にアクセスして使用Storageするには、リムーバブル アクセスコントロールまたはMicrosoft 365 E3必要Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="96547-258">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="96547-259">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="96547-259">Permission</span></span>

<span data-ttu-id="96547-260">Intune でのポリシーの展開では、デバイス構成プロファイルを作成、編集、更新、または削除するためのアクセス許可がアカウントに必要です。</span><span class="sxs-lookup"><span data-stu-id="96547-260">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="96547-261">カスタム ロールを作成するか、これらのアクセス許可を持つ組み込みロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="96547-261">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="96547-262">ポリシーとプロファイル マネージャーの役割</span><span class="sxs-lookup"><span data-stu-id="96547-262">Policy and profile Manager role</span></span>
- <span data-ttu-id="96547-263">デバイス構成プロファイルに対してレポートの作成/編集/更新/読み取り/削除/表示権限を有効にしたカスタム ロール</span><span class="sxs-lookup"><span data-stu-id="96547-263">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="96547-264">全体管理者</span><span class="sxs-lookup"><span data-stu-id="96547-264">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="96547-265">OMA-URI によるポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="96547-265">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="96547-266">**Microsoft エンドポイント マネージャー 管理センター ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 以降 & プロファイル: Custom**</span><span class="sxs-lookup"><span data-stu-id="96547-266">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="96547-267">グループごとに、OMA-URI ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="96547-267">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="96547-268">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="96547-268">OMA-URI:</span></span>

      <span data-ttu-id="96547-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="96547-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="96547-270">たとえば、サンプル **内のリムーバブル 記憶域と CD/DVD** グループの場合、リンクは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="96547-270">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="96547-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="96547-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="96547-272">データ型: 文字列 (XML ファイル)</span><span class="sxs-lookup"><span data-stu-id="96547-272">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="STRING データ型の xml ファイル":::

2. <span data-ttu-id="96547-274">ポリシーごとに、OMA-URI も作成します。</span><span class="sxs-lookup"><span data-stu-id="96547-274">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="96547-275">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="96547-275">OMA-URI:</span></span>

      <span data-ttu-id="96547-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="96547-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="96547-277">たとえば、ブロック書き込みおよび実行アクセスの場合、サンプルで承認 **された USB** ルールを許可するには、次のリンクが必要です。</span><span class="sxs-lookup"><span data-stu-id="96547-277">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="96547-278">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData。</span><span class="sxs-lookup"><span data-stu-id="96547-278">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="96547-279">データ型: 文字列 (XML ファイル)</span><span class="sxs-lookup"><span data-stu-id="96547-279">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="STRING データ型の XML ファイルの表示":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="96547-281">Intune ユーザー インターフェイスを使用したポリシーの展開と管理</span><span class="sxs-lookup"><span data-stu-id="96547-281">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="96547-282">この機能 (Microsoft エンドポイント マネージャー 管理センター ( https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 以降の & Profile: Device Control) はまだ使用できません。</span><span class="sxs-lookup"><span data-stu-id="96547-282">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="96547-283">Microsoft Defender for Endpoint Storageデバイス コントロールリムーバブル アクセス制御データを表示する</span><span class="sxs-lookup"><span data-stu-id="96547-283">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="96547-284">セキュリティ ポータルMicrosoft 365、Device Control リムーバブル アクセス制御によってブロックされたリムーバブル ストレージStorage表示されます。</span><span class="sxs-lookup"><span data-stu-id="96547-284">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="96547-285">セキュリティにアクセスするにはMicrosoft 365サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="96547-285">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="96547-286">Microsoft 365 E5 レポートの詳細</span><span class="sxs-lookup"><span data-stu-id="96547-286">Microsoft 365 for E5 reporting</span></span>

```kusto
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

## <a name="frequently-asked-questions"></a><span data-ttu-id="96547-288">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="96547-288">Frequently asked questions</span></span>

<span data-ttu-id="96547-289">**USB の最大数に対するリムーバブル 記憶域メディアの制限は何ですか?**</span><span class="sxs-lookup"><span data-stu-id="96547-289">**What is the removable storage media limitation for the maximum number of USBs?**</span></span>

<span data-ttu-id="96547-290">100,000 メディアを持つ 1 つの USB グループ (最大 7 MB のサイズ) を検証しました。</span><span class="sxs-lookup"><span data-stu-id="96547-290">We have validated one USB group with 100,000 media - up to 7 MB in size.</span></span> <span data-ttu-id="96547-291">このポリシーは、パフォーマンスの問題なく Intune と GPO の両方で動作します。</span><span class="sxs-lookup"><span data-stu-id="96547-291">The policy works in both Intune and GPO without performance issues.</span></span>

<span data-ttu-id="96547-292">**ポリシーが機能しない理由**</span><span class="sxs-lookup"><span data-stu-id="96547-292">**Why does the policy not work?**</span></span>

<span data-ttu-id="96547-293">最も一般的な理由は、必要な [マルウェア対策クライアントのバージョンがない場合です](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="96547-293">The most common reason is there is no required [antimalware client version](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints).</span></span>

<span data-ttu-id="96547-294">もう 1 つの理由は、XML ファイルの "&" 文字に正しいマークダウン書式を使用しないなど、XML ファイルの形式が正しく設定されていないか、テキスト エディターがファイルの先頭にバイト オーダー マーク (BOM) 0xEF 0xBB 0xBF を追加して XML 解析が機能しないことです。</span><span class="sxs-lookup"><span data-stu-id="96547-294">Another reason could be that the XML file is not correctly formatted, for example, not using the correct markdown formatting for the "&" character in the XML file, or the text editor might add a byte order mark (BOM) 0xEF 0xBB 0xBF at the beginning of the files which causes the XML parsing not to work.</span></span> <span data-ttu-id="96547-295">1 つの簡単な解決策は、サンプル ファイルを [ダウンロード](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) することです **([Raw]** を選択 **し、[名前** を付けて保存] を選択して) 更新します。</span><span class="sxs-lookup"><span data-stu-id="96547-295">One simple solution is to download the [sample file](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (select **Raw** and then **Save as**) and then update.</span></span>

<span data-ttu-id="96547-296">値が指定され、ポリシーがグループ ポリシーによって管理されている場合は、クライアント デバイスがポリシー XML パスにアクセスできるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="96547-296">If there is a value and the policy is managed via Group Policy, check whether the client device can access the policy XML path.</span></span>

<span data-ttu-id="96547-297">**組織で最新のマルウェア対策クライアント バージョンを使用しているコンピューターを確認する方法**</span><span class="sxs-lookup"><span data-stu-id="96547-297">**How can I know which machine is using out of date antimalware client version in the organization?**</span></span>

<span data-ttu-id="96547-298">次のクエリを使用して、セキュリティ ポータルでマルウェア対策クライアントのMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="96547-298">You can use following query to get antimalware client version on the Microsoft 365 security portal:</span></span>
```kusto
//check the antimalware client version
DeviceFileEvents
| where FileName == "MsMpEng.exe"
| where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
| extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//| project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
| summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
| order by PlatformVersion desc
```
