---
title: Office 365 でメール メッセージを暗号化するためにメール フロー ルールを定義する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: 管理者は、Office 365 メッセージ暗号化を使用してメッセージを暗号化および復号化するメールフロールール (トランスポートルール) を作成する方法を学習できます。
ms.openlocfilehash: 80bdd479ec09f0ecefd2758e2b8012a1a7351d6c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42075874"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a><span data-ttu-id="7dc47-103">Office 365 でメール メッセージを暗号化するためにメール フロー ルールを定義する</span><span class="sxs-lookup"><span data-stu-id="7dc47-103">Define mail flow rules to encrypt email messages in Office 365</span></span>

<span data-ttu-id="7dc47-104">Office 365 全体管理者は、メールフロールール (トランスポートルールとも呼ばれます) を作成して、送受信する電子メールメッセージを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="7dc47-104">As an Office 365 global administrator, you can create mail flow rules (also known as transport rules) to help protect email messages you send and receive.</span></span> <span data-ttu-id="7dc47-105">送信電子メールメッセージを暗号化したり、組織内から送信される暗号化されたメッセージから暗号化を削除したり、組織から送信された暗号化メッセージへの返信を削除したりするためのルールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="7dc47-105">You can set up rules to encrypt any outgoing email messages and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> <span data-ttu-id="7dc47-106">これらのルールを作成するには、Exchange 管理センター (EAC) または Exchange Online PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7dc47-106">You can use the Exchange admin center (EAC) or Exchange Online PowerShell to create these rules.</span></span> <span data-ttu-id="7dc47-107">全体的な暗号化ルールに加えて、エンド ユーザー用に個別のメッセージの暗号化オプションの有効化/無効化を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="7dc47-107">In addition to overall encryption rules, you can also choose to enable or disable individual message encryption options for end-users.</span></span>

<span data-ttu-id="7dc47-108">組織外の送信者からの受信メールを暗号化することはできません。</span><span class="sxs-lookup"><span data-stu-id="7dc47-108">You can't encrypt inbound mail from senders outside of your organization.</span></span>

<span data-ttu-id="7dc47-109">AD RMS から Azure Information Protection に最近移行した場合は、既存のメールフロールールを確認して、新しい環境で引き続き動作するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dc47-109">If you recently migrated from AD RMS to Azure Information Protection, you'll need to review your existing mail flow rules to ensure that they continue to work in your new environment.</span></span> <span data-ttu-id="7dc47-110">さらに、Azure Information Protection を使用して利用できる新しい Office 365 Message Encryption (OME) 機能を利用する場合は、既存のメールフロールールを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dc47-110">Additionally, if you want to take advantage of the new Office 365 Message Encryption (OME) capabilities available to you through Azure Information Protection, you need to update your existing mail flow rules.</span></span> <span data-ttu-id="7dc47-111">そうしないと、ユーザーは、新しいシームレスな OME の操作ではなく、前の HTML 添付ファイル形式を使用する暗号化メールを引き続き受信できます。</span><span class="sxs-lookup"><span data-stu-id="7dc47-111">Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience.</span></span> <span data-ttu-id="7dc47-112">まだ OME をセットアップしていない場合は、「 [Office の新しい365メッセージ暗号化機能を設定](set-up-new-message-encryption-capabilities.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-112">If you haven't set up OME yet, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md) for information.</span></span>

<span data-ttu-id="7dc47-113">メールフロールールを構成するコンポーネントと、メールフロールールのしくみについては、「 [Exchange Online のメールフロールール (トランスポートルール)](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-113">For information about the components that make up mail flow rules and how mail flow rules work, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span> <span data-ttu-id="7dc47-114">メールフロールールが Azure Information Protection でどのように機能するかの詳細については、「 [Azure Information protection のラベルの Exchange Online メールフロールールの構成](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-114">For additional information about how mail flow rules work with Azure Information Protection, see [Configuring Exchange Online mail flow rules for Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7dc47-115">ハイブリッド Exchange 環境では、オンプレミスのユーザーは、電子メールが Exchange Online を経由してルーティングされる場合にのみ、OME を使用して暗号化されたメールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="7dc47-115">For hybrid Exchange environments, on-premises users can send encrypted mail using OME only if email is routed through Exchange Online.</span></span> <span data-ttu-id="7dc47-116">ハイブリッド Exchange 環境で OME を構成するには、まず[ハイブリッド構成ウィザードを使用してハイブリッドを構成](https://docs.microsoft.com/Exchange/exchange-hybrid)し、次に、[電子メールサーバーから Office 365 にメールが流れるように構成](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dc47-116">To configure OME in a hybrid Exchange environment, you need to first [configure hybrid using the Hybrid Configuration wizard](https://docs.microsoft.com/Exchange/exchange-hybrid) and then [configure mail to flow from your email server to Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365).</span></span> <span data-ttu-id="7dc47-117">Office 365 を通過するようにメールを構成したら、このガイダンスを使用して OME のメールフロールールを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7dc47-117">Once you've configured mail to flow through Office 365, then you can configure mail flow rules for OME by using this guidance.</span></span>

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="7dc47-118">メールフロールールを作成して、新しい OME 機能で電子メールメッセージを暗号化する</span><span class="sxs-lookup"><span data-stu-id="7dc47-118">Create mail flow rules to encrypt email messages with the new OME capabilities</span></span>

<span data-ttu-id="7dc47-119">EAC を使用して、新しい OME 機能でメッセージの暗号化をトリガーするためのメールフロールールを定義できます。</span><span class="sxs-lookup"><span data-stu-id="7dc47-119">You can define mail flow rules for triggering message encryption with the new OME capabilities by using the EAC.</span></span>

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="7dc47-120">EAC を使用して、新しい OME 機能で電子メールメッセージを暗号化するためのルールを作成する</span><span class="sxs-lookup"><span data-stu-id="7dc47-120">Use the EAC to create a rule for encrypting email messages with the new OME capabilities</span></span>

1. <span data-ttu-id="7dc47-121">Web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-121">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="7dc47-122">[**管理**] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-122">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="7dc47-123">Microsoft 365 管理センターで、[**管理センター** \> ] [ **Exchange**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-123">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="7dc47-124">EAC で、[**メールフロー** \> ] [**ルール**] に移動し **、[新しい\*\* ![新規作成] アイコン](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \>を選択して**新しいルールを作成\*\*します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-124">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="7dc47-125">EAC の使用方法の詳細については、「exchange [Online の exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-125">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="7dc47-126">[**名前**] にルールの名前 (DrToniRamos@hotmail.com のメールの暗号化など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-126">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="7dc47-p106">**[次の場合、このルールを適用する]** で条件を選択し、必要に応じて値を入力します。たとえば、DrToniRamos@hotmail.com 宛のメッセージを暗号化するには、以下のようにします。</span><span class="sxs-lookup"><span data-stu-id="7dc47-p106">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="7dc47-129">**[次の場合、このルールを適用する]** で、**[受信者]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-129">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="7dc47-130">連絡先リストから既存の名前を選択するか、**[名前の確認]** ボックスに新しい電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-130">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="7dc47-131">既存の名前を選択する場合は、一覧から名前を選択してから **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7dc47-131">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="7dc47-132">新しい名前を入力するには、[**名前の確認**] ボックスに電子メールアドレスを入力し、[**名前** \>の確認 **]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-132">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="7dc47-133">他の条件を追加するには、[**その他のオプション**] を選択し、[**条件の追加**] を選択して、一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-133">To add more conditions, choose **More options** and then choose **add condition** and select from the list.</span></span>

   <span data-ttu-id="7dc47-134">たとえば、受信者が組織の外部にいる場合にのみルールを適用するには、[**条件の追加**] を選択し、[**受信者が外部/内部** \>の**組織** \>外にある **]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-134">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="7dc47-135">新しい OME 機能を使用して暗号化を有効にするには、**次の操作を行い**ます。次に、[**メッセージのセキュリティを変更**する] を選択し、[ **Office 365 メッセージの暗号化と権限保護を適用**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-135">To enable encryption using the new OME capabilities, from **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="7dc47-136">一覧から RMS テンプレートを選択し、[**保存**] を選択して、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-136">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
  <span data-ttu-id="7dc47-137">テンプレートの一覧には、既定のテンプレートとオプションのすべてに加えて、Office 365 で使用するために作成したカスタムテンプレートがすべて含まれています。</span><span class="sxs-lookup"><span data-stu-id="7dc47-137">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="7dc47-138">リストが空の場合は、「office の[365 新しいメッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」の説明に従って、Office 365 メッセージの暗号化を新しい機能で設定していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-138">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="7dc47-139">既定のテンプレートの詳細については、「 [Azure Information Protection 用のテンプレートを構成および管理](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-139">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="7dc47-140">[**転送**しない] オプションの詳細については、「[メールの転送オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)を送信しない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-140">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="7dc47-141">[**暗号化のみ**] オプションの詳細については、「[電子メールの暗号化のみオプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-141">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

  <span data-ttu-id="7dc47-142">別のアクションを指定する場合は、[**アクションの追加**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7dc47-142">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a><span data-ttu-id="7dc47-143">EAC を使用して既存のメールフロールールを更新し、新しい OME 機能を使用する</span><span class="sxs-lookup"><span data-stu-id="7dc47-143">Use the EAC to update an existing mail flow rule to use the new OME capabilities</span></span>

1. <span data-ttu-id="7dc47-144">Web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-144">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="7dc47-145">[**管理**] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-145">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="7dc47-146">Microsoft 365 管理センターで、[**管理センター** \> ] [ **Exchange**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-146">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="7dc47-147">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-147">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

5. <span data-ttu-id="7dc47-148">メールフロールールの一覧で、新しい OME 機能を使用するように変更するルールを選択し、[編集] ![[編集](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) **] アイコンを選択**します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-148">In the list of mail flow rules, select the rule you want to modify to use the new OME capabilities and then choose **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>

6. <span data-ttu-id="7dc47-149">新しい OME 機能を使用して暗号化を有効にするには、**次の操作を行い**ます。次に、[**メッセージのセキュリティを変更**する] を選択し、[ **Office 365 メッセージの暗号化と権限保護を適用**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-149">To enable encryption using the new OME capabilities, from **Do the following**, choose **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="7dc47-150">一覧から RMS テンプレートを選択し、[**保存**] を選択して、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-150">Select an RMS template from the list, choose **Save** and then choose **OK**.</span></span>

   <span data-ttu-id="7dc47-151">テンプレートの一覧には、既定のテンプレートとオプションのすべてに加えて、Office 365 で使用するために作成したカスタムテンプレートがすべて含まれています。</span><span class="sxs-lookup"><span data-stu-id="7dc47-151">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="7dc47-152">リストが空の場合は、「 [Azure Information Protection の上に構築された新しい office 365 メッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」に記載されているように、新しい機能を使用して Office 365 メッセージの暗号化を設定していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-152">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="7dc47-153">既定のテンプレートの詳細については、「 [Azure Information Protection 用のテンプレートを構成および管理](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-153">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="7dc47-154">[**転送**しない] オプションの詳細については、「[メールの転送オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)を送信しない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-154">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="7dc47-155">[**暗号化のみ**] オプションの詳細については、「[電子メールの暗号化のみオプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-155">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="7dc47-156">別のアクションを指定する場合は、[**アクションの追加**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7dc47-156">You can choose **add action** if you want to specify another action.</span></span>

7. <span data-ttu-id="7dc47-157">[**実行**する処理] で、**メッセージセキュリティ** \>を変更するために割り当てられているアクションを削除します。**以前のバージョンの OME を適用**します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-157">From the **Do the following** list, remove any actions that are assigned to **Modify the message security** \> **Apply the previous version of OME**.</span></span>

8. <span data-ttu-id="7dc47-158">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-158">Choose **Save**.</span></span>

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a><span data-ttu-id="7dc47-159">新しい機能を使用せずに Office 365 メッセージ暗号化のメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="7dc47-159">Create mail flow rules for Office 365 Message Encryption without the new capabilities</span></span>

<span data-ttu-id="7dc47-160">Office 365 組織を新しい OME 機能にまだ移行していない場合は、これらのタスクを使用して、組織のメッセージを暗号化するためのメールフロールールを定義します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-160">If you haven't yet moved your Office 365 organization to the new OME capabilities, use these tasks to define mail flow rules to encrypt messages for your organization.</span></span> <span data-ttu-id="7dc47-161">Microsoft は、組織にとって適切であることをすぐに、新しい OME 機能に移行するための計画を立てることを推奨します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-161">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="7dc47-162">手順については、「 [Azure Information Protection の上に構築された新しい Office 365 メッセージ暗号化機能のセットアップ](set-up-new-message-encryption-capabilities.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-162">For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span>

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="7dc47-163">EAC を使用して、新しい OME 機能を使用せずに電子メールメッセージを暗号化するためのメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="7dc47-163">Use the EAC to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="7dc47-164">Web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-164">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="7dc47-165">[**管理**] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-165">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="7dc47-166">Microsoft 365 管理センターで、[**管理センター** \> ] [ **Exchange**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-166">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="7dc47-167">EAC で、[**メールフロー** \> ] [**ルール**] に移動し **、[新しい\*\* ![新規作成] アイコン](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \>を選択して**新しいルールを作成\*\*します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-167">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="7dc47-168">EAC の使用方法の詳細については、「exchange [Online の exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-168">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="7dc47-169">[**名前**] にルールの名前 (DrToniRamos@hotmail.com のメールの暗号化など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-169">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="7dc47-p113">**[次の場合、このルールを適用する]** で条件を選択し、必要に応じて値を入力します。たとえば、DrToniRamos@hotmail.com 宛のメッセージを暗号化するには、以下のようにします。</span><span class="sxs-lookup"><span data-stu-id="7dc47-p113">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="7dc47-172">**[次の場合、このルールを適用する]** で、**[受信者]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-172">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="7dc47-173">連絡先リストから既存の名前を選択するか、**[名前の確認]** ボックスに新しい電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-173">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="7dc47-174">既存の名前を選択する場合は、一覧から名前を選択してから **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7dc47-174">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="7dc47-175">新しい名前を入力するには、[**名前の確認**] ボックスに電子メールアドレスを入力し、[**名前** \>の確認 **]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-175">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="7dc47-176">さらに条件を追加するには、[**その他のオプション**] を選択し、[**条件の追加**] を選択してリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-176">To add more conditions, choose **More options** and then select **add condition** and select from the list.</span></span>

   <span data-ttu-id="7dc47-177">たとえば、受信者が組織の外部にいる場合にのみルールを適用するには、[**条件の追加**] を選択し、[**受信者が外部/内部** \>の**組織** \>外にある **]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-177">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="7dc47-178">新しい OME 機能を使用せずに暗号化を有効にするには、**次の操作を行い**ます。 [**メッセージセキュリティ** \>を変更する] [**前のバージョンの OME を適用**する]、[**保存**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-178">To enable encryption without using the new OME capabilities, in **Do the following**, select **Modify the message security** \> **Apply the previous version of OME**, and then choose **Save**.</span></span>

  <span data-ttu-id="7dc47-179">IRM ライセンスが有効になっていないというエラーが表示された場合は、まだ組織の OME をセットアップしていません。</span><span class="sxs-lookup"><span data-stu-id="7dc47-179">If you receive an error that IRM licensing isn't enabled, then you haven't set up OME for your organization yet.</span></span> <span data-ttu-id="7dc47-180">今すぐ OME を設定したい場合は、新しい OME 機能を使用するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dc47-180">If you'd like to set up OME now, you must set it up to use the new OME capabilities.</span></span> <span data-ttu-id="7dc47-181">詳細については、「 [Azure Information Protection の上に構築された新しい Office 365 メッセージ暗号化機能のセットアップ](set-up-new-message-encryption-capabilities.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-181">For information, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="7dc47-182">Microsoft では、新しい機能なしで OME の新しい展開をセットアップすることはサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7dc47-182">Microsoft no longer supports setting up new deployments of OME without the new capabilities.</span></span>

  <span data-ttu-id="7dc47-183">別のアクションを指定する場合は、[**アクションの追加**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7dc47-183">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="7dc47-184">Exchange Online の PowerShell を使用して、新しい OME 機能なしで電子メールメッセージを暗号化するためのメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="7dc47-184">Use Exchange Online PowerShell to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="7dc47-185">Exchange Online PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-185">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="7dc47-186">詳細については、「[Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-186">For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7dc47-187">**New-transportrule**コマンドレットを使用してルールを作成し、 _ApplyOME_パラメーターをに`$true`設定します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-187">Create a rule by using the **New-TransportRule** cmdlet and set the _ApplyOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="7dc47-188">この例では、DrToniRamos@hotmail.com に送信されるすべての電子メールメッセージが暗号化されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dc47-188">This example requires that all email messages sent to DrToniRamos@hotmail.com must be encrypted.</span></span>

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   <span data-ttu-id="7dc47-189">**注**:</span><span class="sxs-lookup"><span data-stu-id="7dc47-189">**Notes**:</span></span>

   - <span data-ttu-id="7dc47-190">新しいルールの一意の名前は、"Dr Toni Ramos の暗号化ルール" です。</span><span class="sxs-lookup"><span data-stu-id="7dc47-190">The unique name of the new rule is "Encrypt rule for Dr Toni Ramos".</span></span>

   - <span data-ttu-id="7dc47-191">パラメーター_に_は、メッセージの受信者を指定します (名前、電子メールアドレス、識別名などで識別されます)。</span><span class="sxs-lookup"><span data-stu-id="7dc47-191">The _SentTo_ parameter specifies the message recipients (identified by name, email address, distinguished name, etc.).</span></span> <span data-ttu-id="7dc47-192">この例では、受信者は電子メールアドレス "DrToniRamos@hotmail.com" によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="7dc47-192">In this example, the recipient is identified by the email address "DrToniRamos@hotmail.com".</span></span>

   - <span data-ttu-id="7dc47-193">/は、メッセージの受信者の場所を_指定します_。</span><span class="sxs-lookup"><span data-stu-id="7dc47-193">The _SentToScope_ parameter specifies the location of the message recipients.</span></span> <span data-ttu-id="7dc47-194">この例では、受信者のメールボックスは hotmail にあり、Office 365 組織の一部ではないため`NotInOrganization` 、値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7dc47-194">In this example, the recipient's mailbox is in hotmail and is not part of the Office 365 organization, so the value `NotInOrganization` is used.</span></span>

   <span data-ttu-id="7dc47-195">構文およびパラメーターの詳細については、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-195">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="7dc47-196">新しい OME 機能を使用せずに暗号化された電子メールの返信から暗号化を削除する</span><span class="sxs-lookup"><span data-stu-id="7dc47-196">Remove encryption from email replies encrypted without the new OME capabilities</span></span>

<span data-ttu-id="7dc47-197">電子メール ユーザーが暗号化メッセージを送信した場合、これらのメッセージの受信者は、暗号化された返信で応答することができます。</span><span class="sxs-lookup"><span data-stu-id="7dc47-197">When your email users send encrypted messages, recipients of those messages can respond with encrypted replies.</span></span> <span data-ttu-id="7dc47-198">メールフロールールを作成して、返信からの暗号化を自動的に削除することで、組織内の電子メールユーザーが暗号化ポータルにサインインして表示されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="7dc47-198">You can create mail flow rules to automatically remove encryption from replies so email users in your organization don't have to sign in to the encryption portal to view them.</span></span> <span data-ttu-id="7dc47-199">これらのルールは、EAC または Windows PowerShell コマンドレットを使用して定義できます。</span><span class="sxs-lookup"><span data-stu-id="7dc47-199">You can use the EAC or Windows PowerShell cmdlets to define these rules.</span></span> <span data-ttu-id="7dc47-200">新しい OME 機能をまだ使用していない場合は、組織内から送信されたメッセージまたは組織内から送信されたメッセージに返信されるメッセージの暗号化を解除することしかできません。</span><span class="sxs-lookup"><span data-stu-id="7dc47-200">If you are not yet using the new OME capabilities, you can only decrypt messages that are either sent from within your organization or messages that are replies to messages sent from within your organization.</span></span> <span data-ttu-id="7dc47-201">組織外からの暗号化されたメッセージを解読することはできません。</span><span class="sxs-lookup"><span data-stu-id="7dc47-201">You cannot decrypt encrypted messages originating from outside of your organization.</span></span>

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="7dc47-202">EAC を使用して、新しい OME 機能を使用せずに暗号化された電子メールの返信からの暗号化を削除するためのルールを作成する</span><span class="sxs-lookup"><span data-stu-id="7dc47-202">Use the EAC to create a rule for removing encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="7dc47-203">Web ブラウザーで、管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-203">In a web browser, using a work or school account that has been granted admin permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="7dc47-204">[**管理**] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-204">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="7dc47-205">Microsoft 365 管理センターで、[**管理センター** \> ] [ **Exchange**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-205">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="7dc47-206">EAC で、[**メールフロー** \> ] [**ルール**] に移動し **、[新しい\*\* ![新規作成] アイコン](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \>を選択して**新しいルールを作成\*\*します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-206">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="7dc47-207">EAC の使用方法の詳細については、「exchange [Online の exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-207">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="7dc47-208">[**名前**] にルールの名前を入力します。たとえば、[受信メールからの暗号化の削除] などです。</span><span class="sxs-lookup"><span data-stu-id="7dc47-208">In **Name**, type a name for the rule, such as Remove encryption from incoming mail.</span></span>

6. <span data-ttu-id="7dc47-209">[**次の場合、このルールを適用**する] [**受信者が** \> **組織内**にある] など、メッセージから暗号化を削除する条件を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-209">In **Apply this rule if** select the conditions where encryption should be removed from messages, such as **The recipient is located** \> **Inside the organization**.</span></span>

7. <span data-ttu-id="7dc47-210">[**実行する処理**] で、[**メッセージのセキュリティ** \>を変更する] を選択します。**以前のバージョンの OME を削除**します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-210">In **Do the following**, select **Modify the message security** \> **Remove the previous version of OME**.</span></span>

8. <span data-ttu-id="7dc47-211">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-211">Select **Save**.</span></span>

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="7dc47-212">Exchange Online PowerShell を使用して、新しい OME 機能なしで暗号化された電子メールの返信から暗号化を削除するルールを作成する</span><span class="sxs-lookup"><span data-stu-id="7dc47-212">Use Exchange Online PowerShell to create a rule to remove encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="7dc47-213">Exchange Online PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-213">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="7dc47-214">詳細については、「[Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-214">For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7dc47-215">**New-transportrule**コマンドレットを使用してルールを作成し、 _RemoveOME_パラメーターをに`$true`設定します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-215">Create a rule by using the **New-TransportRule** cmdlet and set the _RemoveOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="7dc47-216">この例では、Office 365 組織内の受信者に送信されるすべてのメールから暗号化を削除します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-216">This example removes the encryption from all mail sent to recipients in the Office 365 organization.</span></span>

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   <span data-ttu-id="7dc47-217">**注**:</span><span class="sxs-lookup"><span data-stu-id="7dc47-217">**Notes**:</span></span>

   - <span data-ttu-id="7dc47-218">新しいルールの一意の名前は、"受信メールから暗号化を削除する" です。</span><span class="sxs-lookup"><span data-stu-id="7dc47-218">The unique name of the new rule is "Remove encryption from incoming mail".</span></span>

   - <span data-ttu-id="7dc47-219">/は、メッセージの受信者の場所を_指定します_。</span><span class="sxs-lookup"><span data-stu-id="7dc47-219">The _SentToScope_ parameter specifies the location of the message recipients.</span></span> <span data-ttu-id="7dc47-220">この例では、値`InOrganization`の値を使用して、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="7dc47-220">In this example, the value `InOrganization` value is used, which indicates:</span></span>

     - <span data-ttu-id="7dc47-221">受信者が組織内のメールボックス、メールユーザー、グループ、またはメールが有効なパブリックフォルダーである。</span><span class="sxs-lookup"><span data-stu-id="7dc47-221">The recipient is a mailbox, mail user, group, or mail-enabled public folder in your organization.</span></span>

       <span data-ttu-id="7dc47-222">または</span><span class="sxs-lookup"><span data-stu-id="7dc47-222">or</span></span>

     - <span data-ttu-id="7dc47-223">受信者の電子メールアドレスが、組織内の権限のあるドメインまたは内部の中継ドメインとして構成さ_れている_承認済みドメイン内にあり、認証された接続を介してメッセージが送信または受信された。</span><span class="sxs-lookup"><span data-stu-id="7dc47-223">The recipient's email address is in an accepted domain that's configured as an authoritative domain or an internal relay domain in your organization, _and_ the message was sent or received over an authenticated connection.</span></span>

<span data-ttu-id="7dc47-224">構文およびパラメーターの詳細については、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc47-224">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7dc47-225">関連項目</span><span class="sxs-lookup"><span data-stu-id="7dc47-225">Related Topics</span></span>

[<span data-ttu-id="7dc47-226">Office 365 での暗号化</span><span class="sxs-lookup"><span data-stu-id="7dc47-226">Encryption in Office 365</span></span>](encryption.md)

[<span data-ttu-id="7dc47-227">新しい Office 365 Message Encryption 機能を設定する</span><span class="sxs-lookup"><span data-stu-id="7dc47-227">Set up new Office 365 Message Encryption capabilities</span></span>](set-up-new-message-encryption-capabilities.md)

[<span data-ttu-id="7dc47-228">暗号化メッセージへのブランドの追加</span><span class="sxs-lookup"><span data-stu-id="7dc47-228">Add branding to encrypted messages</span></span>](add-your-organization-brand-to-encrypted-messages.md)

[<span data-ttu-id="7dc47-229">Exchange Online のメール フロー ルール (トランスポート ルール)</span><span class="sxs-lookup"><span data-stu-id="7dc47-229">Mail flow rules (transport rules) in Exchange Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[<span data-ttu-id="7dc47-230">Exchange Online Protection のメール フロー ルール (トランスポート ルール)</span><span class="sxs-lookup"><span data-stu-id="7dc47-230">Mail flow rules (transport rules) in Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506708)
