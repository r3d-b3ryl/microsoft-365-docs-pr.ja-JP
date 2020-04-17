---
title: EOP で既定のフィッシング対策ポリシーを構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online メールボックスを使用して、Office 365 組織の既定のフィッシング対策ポリシーで利用可能なスプーフィング対策設定を変更する方法を学習できます。
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537535"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a><span data-ttu-id="02f84-103">EOP で既定のフィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="02f84-103">Configure the default anti-phishing policy in EOP</span></span>

<span data-ttu-id="02f84-104">Exchange online メールボックスを使用しない exchange online メールボックスおよびスタンドアロンの Exchange Online Protection (EOP) 組織を使用している Office 365 組織には、既定のフィッシング対策ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="02f84-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes have a default anti-phishing policy.</span></span> <span data-ttu-id="02f84-105">このポリシーには、既定で有効になっている、限られた数のスプーフィング対策機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="02f84-105">This policy contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="02f84-106">詳細については、「[フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f84-106">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="02f84-107">Office 365 Exchange Online メールボックスを使用する組織では、Office 365 セキュリティ & コンプライアンスセンターまたは Exchange Online PowerShell で既定のフィッシング対策ポリシーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="02f84-107">Office 365 organizations with Exchange Online mailboxes can modify the default anti-phishing policy in the Office 365 Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="02f84-108">Exchange Online メールボックスを使用しないスタンドアロン EOP 組織では、既定のフィッシング対策ポリシーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="02f84-108">Standalone EOP organizations without Exchange Online mailboxes can't modify their default anti-phishing policy.</span></span>

<span data-ttu-id="02f84-109">Office 365 Advanced Threat Protection で使用可能な、より高度な ATP のフィッシング対策ポリシーの作成と変更の詳細については、「 [office 365 で ATP のフィッシング対策ポリシーを構成する](configure-atp-anti-phishing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f84-109">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="02f84-110">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="02f84-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="02f84-111"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="02f84-111">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="02f84-112">**フィッシング対策**ページに直接移動するには、を<https://protection.office.com/antiphishing>使用します。</span><span class="sxs-lookup"><span data-stu-id="02f84-112">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="02f84-113">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f84-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="02f84-114">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f84-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="02f84-115">フィッシング対策ポリシーを追加、変更、および削除するには、**組織の管理**または**セキュリティ管理者**の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f84-115">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="02f84-116">フィッシング対策ポリシーに対する読み取り専用アクセスでは、**セキュリティリーダー**役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f84-116">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="02f84-117">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[Office 365 セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="02f84-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="02f84-118">既定のフィッシング対策ポリシーの推奨設定については、「 [EOP default フィッシング対策ポリシーの設定](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f84-118">For our recommended settings for the default anti-phishing policy, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="02f84-119">更新されたポリシーが適用されるまで最大30分かかります。</span><span class="sxs-lookup"><span data-stu-id="02f84-119">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="02f84-120">フィルタリングパイプラインにフィッシング対策ポリシーを適用する方法については、「 [Office 365 での電子メール保護の順序と優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f84-120">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection in Office 365](how-policies-and-protections-are-combined.md).</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="02f84-121">セキュリティ & コンプライアンスセンターを使用して既定のフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="02f84-121">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="02f84-122">既定のフィッシング対策ポリシーの名前は、Office365 フィッシング対策 Default で、ポリシーの一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="02f84-122">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="02f84-123">既定のフィッシング対策ポリシーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="02f84-123">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="02f84-124">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \>の**フィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="02f84-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="02f84-125">[**フィッシング対策**] ページで、[**既定のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02f84-125">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="02f84-126">[**ポリシーの Office 365 フィッシング対策の既定の編集**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="02f84-126">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="02f84-127">[**スプーフィング**] セクションで、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02f84-127">In the **Spoof** section, click **Edit**.</span></span>

   <span data-ttu-id="02f84-128">これらの設定は、ATP のフィッシング対策ポリシーで使用可能なスプーフィング設定と同じであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="02f84-128">Note that these settings are identical to the spoof settings that are available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="02f84-129">**フィルター設定のスプーフィング**: 既定値は**on**で、そのままにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="02f84-129">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="02f84-130">この機能をオフにするには、トグルを [**オフ**] にします。</span><span class="sxs-lookup"><span data-stu-id="02f84-130">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="02f84-131">詳細については、「 [Configure スプーフ知能 In Office 365](learn-about-spoof-intelligence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f84-131">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="02f84-132">MX レコードが Office 365 を指していない場合は、スプーフィング対策保護を無効にする必要はありません。代わりに、コネクタの拡張フィルターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="02f84-132">You don't need to disable anti-spoofing protection if your MX record doesn't point to Office 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="02f84-133">手順については、「 [Exchange Online のコネクタの拡張フィルター処理](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f84-133">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="02f84-134">[認証されていない**送信者機能を有効にする**]: メッセージが電子メール認証チェックに失敗した場合に、送信者の写真に疑問符を追加します。</span><span class="sxs-lookup"><span data-stu-id="02f84-134">**Enable Unauthenticated Sender feature**: Adds a question mark to the sender's photo if the message fails email authentication checks.</span></span> <span data-ttu-id="02f84-135">詳細については、「[フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f84-135">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span> <span data-ttu-id="02f84-136">既定値は [**オン**] です。</span><span class="sxs-lookup"><span data-stu-id="02f84-136">The default value is **On**.</span></span> <span data-ttu-id="02f84-137">この機能をオフにするには、トグルを [**オフ**] にします。</span><span class="sxs-lookup"><span data-stu-id="02f84-137">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="02f84-138">**アクション**: スプーフィングインテリジェンスに失敗したメッセージに対して実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="02f84-138">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="02f84-139">**ドメインのスプーフィングが許可されていないユーザーによって電子メールが送信**される場合:</span><span class="sxs-lookup"><span data-stu-id="02f84-139">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="02f84-140">**受信者の迷惑メールフォルダーにメッセージを移動**します (これは既定値です)。</span><span class="sxs-lookup"><span data-stu-id="02f84-140">**Move message to the recipients' Junk Email folders** (This is the default value.)</span></span>
     - <span data-ttu-id="02f84-141">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="02f84-141">**Quarantine the message**</span></span>

   - <span data-ttu-id="02f84-142">**設定を確認**します。個々の手順をクリックする代わりに、設定が概要で表示されます。</span><span class="sxs-lookup"><span data-stu-id="02f84-142">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="02f84-143">各セクションで [**編集**] をクリックすると、関連するページに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="02f84-143">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="02f84-144">このページでは、次の設定の**オン**と**オフ**を直接切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="02f84-144">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="02f84-145">**スプーフィング対策保護を有効にする**</span><span class="sxs-lookup"><span data-stu-id="02f84-145">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="02f84-146">**認証されていない送信者機能を有効にする**</span><span class="sxs-lookup"><span data-stu-id="02f84-146">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="02f84-147">完了したら、[任意のページに**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02f84-147">When you're finished, click **Save** on any page.</span></span>

4. <span data-ttu-id="02f84-148">[Policy を**編集する Office365 フィッシング対策 Default** ] ページに戻り、設定を確認してから [**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02f84-148">Back on the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a><span data-ttu-id="02f84-149">セキュリティ & コンプライアンスセンターを使用して既定のフィッシング対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="02f84-149">Use the Security & Compliance Center to view the default anti-phishing policy</span></span>

1. <span data-ttu-id="02f84-150">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="02f84-150">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="02f84-151">[**既定のポリシー** ] をクリックして、既定のフィッシング対策ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="02f84-151">Click **Default policy** to view the default anti-phishing policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a><span data-ttu-id="02f84-152">Exchange Online の PowerShell を使用して既定のフィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="02f84-152">Use Exchange Online PowerShell to configure the default anti-phishing policy</span></span>

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a><span data-ttu-id="02f84-153">PowerShell を使用して既定のフィッシングポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="02f84-153">Use PowerShell to view the default anti-phish policy</span></span>

<span data-ttu-id="02f84-154">既定のフィッシングポリシーを表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="02f84-154">To view the default anti-phish policy, run the following command:</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

<span data-ttu-id="02f84-155">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f84-155">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a><span data-ttu-id="02f84-156">PowerShell を使用して既定のフィッシングポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="02f84-156">Use PowerShell to modify the default anti-phish policy</span></span>

<span data-ttu-id="02f84-157">既定のフィッシングポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02f84-157">To modify the default anti-phish policy, use the following syntax:</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="02f84-158">この例では、認証チェックに失敗したスプーフィングされたメッセージに対するアクションを、検疫に変更します。</span><span class="sxs-lookup"><span data-stu-id="02f84-158">This example changes the action for spoofed messages that fail authentication checks to quarantine.</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="02f84-159">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f84-159">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="02f84-160">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="02f84-160">How do you know these procedures worked?</span></span>

<span data-ttu-id="02f84-161">既定のフィッシング対策ポリシーが正常に構成されたことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="02f84-161">To verify that you've successfully configured the default anti-phishing policy, do any of the following steps:</span></span>

- <span data-ttu-id="02f84-162">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \>の**フィッシング** \>対策] に移動し、[**既定のポリシー** ] をクリックして、フライアウトの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="02f84-162">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="02f84-163">Exchange Online PowerShell で次のコマンドを実行し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="02f84-163">In Exchange Online PowerShell, run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
