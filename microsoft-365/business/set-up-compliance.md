---
title: Microsoft 365 Business の脅威保護を強化する
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Office 365 Advanced Threat Protection を設定し、機密データを保護します。
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668395"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="a47a4-103">コンプライアンス機能を設定する</span><span class="sxs-lookup"><span data-stu-id="a47a4-103">Set up compliance features</span></span>

<span data-ttu-id="a47a4-104">Microsoft 365 Business には、データとデバイスを保護するための機能が用意されており、お客様の機密情報を安全に保つために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a47a4-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="a47a4-105">DLP 機能を設定する</span><span class="sxs-lookup"><span data-stu-id="a47a4-105">Set up DLP features</span></span>

<span data-ttu-id="a47a4-106">個人を特定できる情報 (PII) を保護するポリシーを設定する方法の例については、「[テンプレートからの DLP ポリシーの作成](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a47a4-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="a47a4-107">DLP には、さまざまなロケールに対して、多くの使用可能なポリシーテンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a47a4-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="a47a4-108">たとえば、オーストラリアの財務データ、カナダの個人情報法、米国金融データなど。完全なリストについては[、DLP ポリシーテンプレートに含まれるもの](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a47a4-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="a47a4-109">これらのテンプレートはすべて、PII テンプレートの例と同様に有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a47a4-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="a47a4-110">Exchange Online アーカイブを使用したメールの保存期間の設定</span><span class="sxs-lookup"><span data-stu-id="a47a4-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="a47a4-111">**Exchange Online のアーカイブ**ライセンス機能は、電子情報開示用の電子メールコンテンツを保持することで、コンプライアンスおよび規制基準を維持するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a47a4-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="a47a4-112">また、訴訟が発生した場合のリスクを軽減し、セキュリティ違反の後で、または削除済みアイテムを復元する必要がある場合にも、データを回復することができます。</span><span class="sxs-lookup"><span data-stu-id="a47a4-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="a47a4-113">訴訟ホールドを使用して、ユーザーのすべてのコンテンツを保持するか、保持ポリシーを使用して、保持する内容をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="a47a4-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="a47a4-114">**訴訟ホールド:** ユーザーのメールボックスを訴訟ホールドの対象にすることで、削除されたアイテムを含むすべてのメールボックスのコンテンツを保持できます。</span><span class="sxs-lookup"><span data-stu-id="a47a4-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="a47a4-115">メールボックスを訴訟ホールドの対象にするには、管理センターで次のようにします。</span><span class="sxs-lookup"><span data-stu-id="a47a4-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="a47a4-116">左側のナビゲーションで、[**ユーザー** \> ] [**アクティブなユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="a47a4-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="a47a4-117">訴訟ホールドの対象とするメールボックスを持つユーザーを選択し、ユーザーウィンドウで [**メールの設定**] を展開し、[**その他の設定**] の横にある [ **Exchange プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a47a4-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="a47a4-118">ユーザーのメールボックスページで、左側のナビゲーションにある [\* \* メールボックスの機能] を選択し、[**訴訟ホールド**] の下の [**有効にする**] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="a47a4-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="a47a4-119">[**訴訟**ホールド] ダイアログボックスで、[**訴訟ホールド期間**] フィールドに訴訟ホールド期間を指定することができます。無限に保持する場合は、フィールドを空のままにします。</span><span class="sxs-lookup"><span data-stu-id="a47a4-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="a47a4-120">また、メモを追加して、メールボックスの所有者を web サイトに誘導することもできます。 \>これにより、訴訟ホールドの**保存**について詳細に説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a47a4-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="a47a4-121">**保持:** 保持期間の終了時に、特定の時間だけ保持したり、コンテンツを完全に削除したりするために、カスタマイズされた保持ポリシーを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a47a4-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="a47a4-122">詳細については、「[アイテム保持ポリシーの概要](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a47a4-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-azure-information-protection-features"></a><span data-ttu-id="a47a4-123">Azure Information Protection 機能をセットアップする</span><span class="sxs-lookup"><span data-stu-id="a47a4-123">Set up Azure Information Protection features</span></span>

<span data-ttu-id="a47a4-124">Azure Information Protection (AIP) は、ラベルを適用することにより、ドキュメントや電子メールを分類し、必要に応じて保護します。</span><span class="sxs-lookup"><span data-stu-id="a47a4-124">Azure Information Protection (AIP) helps you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="a47a4-125">ラベルは、ルールと条件を定義する管理者、またはユーザーによって手動で、またはユーザーに推奨事項を与える組み合わせを使用して、自動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="a47a4-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="a47a4-126">Web 上の Outlook では、次の組み込みのラベルと制限を電子メールに適用できます。</span><span class="sxs-lookup"><span data-stu-id="a47a4-126">In Outlook on the web you can apply the following built-in labels and restrictions to your emails:</span></span>
  
- <span data-ttu-id="a47a4-127">**転送不可**: 受信者はメッセージを読み取ることはできますが、コンテンツを転送、印刷、またはコピーすることはできません</span><span class="sxs-lookup"><span data-stu-id="a47a4-127">**Do Not Forward**: Recipients can read the message, but they can't forward, print, or copy content</span></span>
    
- <span data-ttu-id="a47a4-128">**Encrypt**: メッセージ全体が暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="a47a4-128">**Encrypt**: The entire message is encrypted.</span></span> <span data-ttu-id="a47a4-129">暗号化されたコンテンツにアクセスする前に自分の id を確認する必要があり、暗号化を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="a47a4-129">Recipients must confirm their identity before accessing encrypted content and can't remove encryption.</span></span>
    
- <span data-ttu-id="a47a4-130">**社外秘**: 組織内の従業員に電子メールのコンテンツと添付ファイルへの完全なアクセス許可は付与されますが、組織外のユーザーに対しては含まれません。</span><span class="sxs-lookup"><span data-stu-id="a47a4-130">**Confidential**: Gives the employees in your organization full permissions to the email content and attachments, but not to people outside your organization.</span></span> <span data-ttu-id="a47a4-131">データ所有者は、任意の時点でコンテンツを追跡して取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="a47a4-131">Data owners can track and revoke content at any point.</span></span>
    
- <span data-ttu-id="a47a4-132">**高機密**: この制限は機密性の高いデータに適用できるため、従業員はデータの表示、編集、および返信を行うことはできませんが、転送、印刷、またはコピーはできません。</span><span class="sxs-lookup"><span data-stu-id="a47a4-132">**Highly Confidential**: This restriction can be applied to highly confidential data, allowing employees to view, edit, and reply, but not forward, print, or copy the data.</span></span> <span data-ttu-id="a47a4-133">データ所有者は、任意の時点でコンテンツを追跡して取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="a47a4-133">Data owners can track and revoke content at any point.</span></span>

### <a name="make-sure-azure-information-protection-is-activated"></a><span data-ttu-id="a47a4-134">Azure Information Protection がアクティブ化されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="a47a4-134">Make sure Azure Information Protection is activated</span></span>

<span data-ttu-id="a47a4-135">AIP がアクティブ化されていることを確認するには</span><span class="sxs-lookup"><span data-stu-id="a47a4-135">To verify that AIP is activated :</span></span>

1. <span data-ttu-id="a47a4-136">[Azure portal](https://portal.azure.com/)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="a47a4-136">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="a47a4-137">[**すべてのサービス**] を選択し、[**検索] ボックス**に「 *Azure Information Protection* 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="a47a4-137">Select **All services** and type in *Azure Information Protection* in the **Search Box**.</span></span>

3. <span data-ttu-id="a47a4-138">結果が表示されたら、 **Azure Information Protection**の横にある [開始] をクリックして、お気に入りにし、後で見つけやすいようにします。</span><span class="sxs-lookup"><span data-stu-id="a47a4-138">Once the results display, click the start next to **Azure Information Protection** to make it a favorite and easy to find later.</span></span>

4. <span data-ttu-id="a47a4-139">[ **Azure Information protection** \> **protection activation** ] を選択し、状態が [アクティブ] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a47a4-139">Select **Azure Information Protection** \> **Protection activation** and make sure the status is set to activated.</span></span> 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a><span data-ttu-id="a47a4-140">Azure Information Protection ポリシーと既定のラベルを表示する</span><span class="sxs-lookup"><span data-stu-id="a47a4-140">View the Azure Information Protection policy and default labels</span></span> 

<span data-ttu-id="a47a4-141">既存のラベルを表示および変更するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="a47a4-141">To view, and modify, the existing labels:</span></span>

1. <span data-ttu-id="a47a4-142">[Azure Information Protection] ダッシュボードで、[**分類** \> **ラベル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a47a4-142">On the Azure Information Protection dashboard, select **Classifications** \> **Labels**.</span></span> <br/><span data-ttu-id="a47a4-143">![Azure Information Protection の標準ラベル。](media/AIPLabels.png)</span><span class="sxs-lookup"><span data-stu-id="a47a4-143">![Standard labels for Azure Information Protection.](media/AIPLabels.png)</span></span>

2. <span data-ttu-id="a47a4-144">任意のラベルを選択してオプションを表示したり、表示名や色などを変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="a47a4-144">You can choose any label to view options, you can change the display name, colors, etc.</span></span>
 
3. <span data-ttu-id="a47a4-145">独自のラベルを作成する場合は、「[変更して新しいラベルを作成](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a47a4-145">See  [Modify and create new labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) if you want to create your own.</span></span> 

### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="a47a4-146">Azure Information Protection クライアントを手動でインストールする</span><span class="sxs-lookup"><span data-stu-id="a47a4-146">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="a47a4-147">AIP クライアントを手動でインストールするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="a47a4-147">To manually install the AIP client:</span></span>

1. <span data-ttu-id="a47a4-148">[Microsoft ダウンロードセンター](https://www.microsoft.com/download/details.aspx?id=53018)から**azinfoprotection**をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a47a4-148">Download **AzInfoProtection.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="a47a4-149">Word 文書を表示し、[**ホーム**] タブで [**保護**] オプションが有効になっていることを確認することで、インストールが正常に行われたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a47a4-149">You can verify that the installation worked by viewing a Word document and making sure that the **Protect** option is available on the **Home** tab.</span></span> <br/><span data-ttu-id="a47a4-150">![Word 文書内の [保護] タブのドロップダウン](media/Word_Protect.png)</span><span class="sxs-lookup"><span data-stu-id="a47a4-150">![Protection tab drop-down in a Word document.](media/Word_Protect.png)</span></span>

<span data-ttu-id="a47a4-151">詳細については、「[クライアントをインストールする](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a47a4-151">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
