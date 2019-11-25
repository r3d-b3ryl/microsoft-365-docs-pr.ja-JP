---
title: 新しい Office 365 Message Encryption 機能を設定する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Azure Information Protection をベースに構築された、Office 365 Message Encryption (OME) の新機能を使用すると、自分の組織で組織内および組織外のユーザーと保護されたメール通信を使用することができます。 OME の新機能は、他の Office 365 組織、Outlook.com、Gmail、およびその他のメール サービスと連携します。
ms.openlocfilehash: c772151250d30e62a3f2689df5cd853536af3ede
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "39218736"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a><span data-ttu-id="5c2ae-104">新しい Office 365 Message Encryption 機能を設定する</span><span class="sxs-lookup"><span data-stu-id="5c2ae-104">Set up new Office 365 Message Encryption capabilities</span></span>

<span data-ttu-id="5c2ae-105">新しい Office 365 Message Encryption (OME) 機能では、保護されたメールを任意のデバイス上の誰とでも共有できます。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-105">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="5c2ae-106">ユーザーは、Outlook.com、Gmail、およびその他のメール サービスを使用して、他の Office 365 組織や Office 365 以外のユーザーと保護されたメッセージを交換できます。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-106">Users can exchange protected messages with other Office 365 organizations, as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="5c2ae-107">Office 365 組織で新しい OME 機能が使用できるようにするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-107">Follow the steps below to ensure that the new OME capabilities are available in your Office 365 organization.</span></span>

## <a name="verify-that-azure-rights-management-is-active"></a><span data-ttu-id="5c2ae-108">Azure Rights Management が有効であることを確認する</span><span class="sxs-lookup"><span data-stu-id="5c2ae-108">Verify that Azure Rights Management is active</span></span>

<span data-ttu-id="5c2ae-109">新しい OME 機能は、[Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/azure/information-protection/what-is-information-protection) の保護機能を活用します。Azure RMS は、[Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) が暗号化とアクセス制御を介して電子メールとドキュメントを保護するために使用するテクノロジーです。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-109">The new OME capabilities leverage the protection features in [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), the technology used by [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) to protect emails and documents via encryption and access controls.</span></span>

<span data-ttu-id="5c2ae-110">新しい OME 機能を使用するための唯一の前提条件は、組織のテナントで [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) を有効化する必要があることです。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-110">The only prerequisite for using the new OME capabilities is that [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) must be activated in your organization's tenant.</span></span> <span data-ttu-id="5c2ae-111">その場合、Office 365 は新しい OME 機能を自動的に有効化するため、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-111">If it is, Office 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="5c2ae-112">また、Azure RMS はほとんどの対象となるプランで自動的に有効化されるため、おそらく何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-112">Azure RMS is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="5c2ae-113">詳細については、「[Azure Rights Management を有効化する](https://docs.microsoft.com/azure/information-protection/activate-service)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-113">See [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/activate-service) for more information.</span></span>

>[!IMPORTANT]
><span data-ttu-id="5c2ae-114">Exchange Online で Active Directory Rights Management サービス (AD RMS) を使用する場合、新しい OME 機能を使用する前に [Azure Information Protection に移行する](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms)必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-114">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="5c2ae-115">OME は、AD RMS と互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-115">OME is not compatible with AD RMS.</span></span>  

<span data-ttu-id="5c2ae-116">詳しくは、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-116">For more information, see:</span></span>

- <span data-ttu-id="5c2ae-117">[新しい OME 機能を使用するには、どのサブスクリプションが必要か](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities)については、サブスクリプションプランに Azure Information Protection (Azure RMS 機能を含む) が含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-117">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes Azure RMS functionality).</span></span>
- <span data-ttu-id="5c2ae-118">対象となるサブスクリプションの購入に関する情報については、「[Azure Information Protection](https://azure.microsoft.com/services/information-protection/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-118">[Azure Information Protection](https://azure.microsoft.com/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-azure-rights-management"></a><span data-ttu-id="5c2ae-119">Azure Rights Management を手動で有効化する</span><span class="sxs-lookup"><span data-stu-id="5c2ae-119">Manually activating Azure Rights Management</span></span>

<span data-ttu-id="5c2ae-120">Azure RMS を無効にした場合、または何らかの理由で自動的に有効化されなかった場合は、次のように手動で有効化できます:</span><span class="sxs-lookup"><span data-stu-id="5c2ae-120">If you disabled Azure RMS, or if it was not automatically activated for any reason, you can activate it manually in the:</span></span>

- <span data-ttu-id="5c2ae-121">**Microsoft 365 管理センター**: 手順については、「[管理センターから Azure Rights Management を有効化する方法](https://docs.microsoft.com/azure/information-protection/activate-office365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-121">**Microsoft 365 admin center**: See [How to activate Azure Rights Management from the admin center](https://docs.microsoft.com/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="5c2ae-122">**Azure Portal**: 手順については、「[Azure Portal から Azure Rights Management を有効化する方法](https://docs.microsoft.com/azure/information-protection/activate-azure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-122">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="5c2ae-123">Azure Information Protection テナント キーの管理を構成する</span><span class="sxs-lookup"><span data-stu-id="5c2ae-123">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="5c2ae-124">この手順は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-124">This is not an optional step.</span></span> <span data-ttu-id="5c2ae-125">Microsoft が Azure Information Protection のルート キーを管理できるようにすることが既定であり、ほとんどの Office 365 テナントに推奨されるベスト プラクティスです。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-125">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most Office 365 tenants.</span></span> <span data-ttu-id="5c2ae-126">このような場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-126">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="5c2ae-127">コンプライアンス要件など、多くの理由により、独自のルート キー (Bring Your Own Key (BYOK) とも呼ばれる)の生成と管理が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-127">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="5c2ae-128">この場合、新しい OME 機能をセットアップする前に、必要な手順を完了することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-128">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="5c2ae-129">詳細については、「[Azure Information Protection テナント キーを計画して実装する](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-129">See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="5c2ae-130">Exchange Online PowerShell で新しい OME 構成を確認する</span><span class="sxs-lookup"><span data-stu-id="5c2ae-130">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="5c2ae-131">[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps) の新しい OME 機能を使用するように Office 365 テナントが適切に構成されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-131">You can verify that your Office 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="5c2ae-132">Office 365 テナントのグローバル管理者権限を持つアカウントを使用して、[Exchange Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-132">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Office 365 tenant.</span></span>

2. <span data-ttu-id="5c2ae-133">Get-IRMConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-133">Run the following cmdlet:</span></span>

     <span data-ttu-id="5c2ae-134">AzureRMSLicensingEnabled パラメーターの $True 値が表示されます。これは、テナントで OME が構成されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-134">You should see a value of $True for the AzureRMSLicensingEnabled parameter, which indicates that OME is configured in your tenant.</span></span> <span data-ttu-id="5c2ae-135">そうでない場合は、Set-IRMConfiguration を使用して AzureRMSLicensingEnabled の値を $ True に設定し、OME を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-135">If it is not, use Set-IRMConfiguration to set the value of AzureRMSLicensingEnabled to $True to enable OME.</span></span>

3. <span data-ttu-id="5c2ae-136">次の構文を使用して Test-IRMConfiguration コマンドレットを実行します:</span><span class="sxs-lookup"><span data-stu-id="5c2ae-136">Run the script by using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="5c2ae-137">**例**:</span><span class="sxs-lookup"><span data-stu-id="5c2ae-137">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="5c2ae-138">送信者の電子メールの提供はオプションですが、システムに追加のチェックを強制的に実行させます。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-138">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="5c2ae-139">Office 365 テナントの任意のユーザーのメール アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-139">Use the email address of any user in your Office 365 tenant.</span></span>

     <span data-ttu-id="5c2ae-140">結果は次のようになります:</span><span class="sxs-lookup"><span data-stu-id="5c2ae-140">Your results should be similar to:</span></span>

     ```text
    Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
    ```

   - <span data-ttu-id="5c2ae-141">*Contoso* は Office 365 の組織名に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-141">Your Office 365 organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="5c2ae-142">既定のテンプレート名は、上に表示されているものとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-142">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="5c2ae-143">詳細については、「[Azure Information Protection のテンプレートを構成して管理する](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-143">See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) for more.</span></span>

4. <span data-ttu-id="5c2ae-144">Rights Management サービスから切断するには、Remove-PSSession コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-144">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="5c2ae-145">次の手順: 新しい OME 機能を使用するためのメール フロー ルールを定義する</span><span class="sxs-lookup"><span data-stu-id="5c2ae-145">Next steps: Define mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="5c2ae-146">Office 365 組織のメールを暗号化するために以前に構成されたメール フロー ルールがある場合は、新しい OME 機能を使用するために既存のルールを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-146">If there are previously configured mail flow rules to encrypt email in your Office 365 organization, you need to update the existing rules to use the new OME capabilities.</span></span> <span data-ttu-id="5c2ae-147">新しい展開の場合、新しいメール フロー ルールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-147">For new deployments, you need to create new mail flow rules.</span></span>

>[!IMPORTANT]
><span data-ttu-id="5c2ae-148">既存のメール フロー ルールを更新しない場合、ユーザーは新しい、シームレスな OME の操作環境ではなく、以前の HTML 添付ファイルの形式を使用する暗号化されたメールを引き続き受信します。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-148">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new seamless OME experience.</span></span>

<span data-ttu-id="5c2ae-149">メール フロー ルールは、メール メッセージを暗号化する条件、およびその暗号化を削除する条件を決定します。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-149">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption.</span></span> <span data-ttu-id="5c2ae-150">ルールのアクションを設定すると、送信時に、ルールの条件に一致するすべてのメッセージが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-150">When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="5c2ae-151">OME のメール フロー ルールの作成の手順については、「[Office 365 でメール メッセージを暗号化するためにメール フロー ルールを定義する](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-151">For steps on creating mail flow rules for OME, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

<span data-ttu-id="5c2ae-152">新しい OME 機能を使用するために既存のルールを更新するには:</span><span class="sxs-lookup"><span data-stu-id="5c2ae-152">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="5c2ae-153">Microsoft 365 管理センターから [**管理センター]、[Exchange**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-153">In the Microsoft 365 admin center, go to Admin centers  Exchange.</span></span>
2. <span data-ttu-id="5c2ae-154">Exchange 管理センターで、[**メール フロー]、[ルール**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-154">In the Exchange admin center (EAC), go to **Mail flow > Rules**.</span></span>
3. <span data-ttu-id="5c2ae-155">ルールごとに、**次の操作を行います**:</span><span class="sxs-lookup"><span data-stu-id="5c2ae-155">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="5c2ae-156">[**メッセージのセキュリティを変更する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-156">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="5c2ae-157">[**Office 365 Message Encryption および適切な保護を適用する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-157">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="5c2ae-158">一覧から RMS テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-158">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="5c2ae-159">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-159">Select **Save**.</span></span>
    - <span data-ttu-id="5c2ae-160">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c2ae-160">Select **OK**.</span></span>
