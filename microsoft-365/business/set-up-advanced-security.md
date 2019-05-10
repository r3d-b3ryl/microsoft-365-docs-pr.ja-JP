---
title: Microsoft 365 Business ユーザーの高度なセキュリティポリシーをセットアップする
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
ms.openlocfilehash: 4728e11a16fdf8a461f5687632df75699923f846
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "33663646"
---
# <a name="set-up-advanced-security-policies"></a><span data-ttu-id="43295-103">高度なセキュリティポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="43295-103">Set up advanced security policies</span></span>

<span data-ttu-id="43295-104">[管理センター](security-features.md#microsoft-365-business-admin-center-security-features)で設定できるポリシーに加えて、 [Office 365 Advanced Threat protection](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653) (ATP) を設定することによって、サイバー脅威に対する保護を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="43295-104">In addition to the policies you can set up in the [admin center](security-features.md#microsoft-365-business-admin-center-security-features), you can add additional protection against cyber threats by setting up [Office 365 Advanced Threat Protection](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653) (ATP).</span></span> <span data-ttu-id="43295-105">また、機密情報を保護するには、[データ損失防止](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)(DLP)、Azure information PROTECTION (AIP)、 [Exchange Online アーカイブ](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)をセットアップして、 [Intune ポータル](#go-to-intune-admin-center)でデバイスを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="43295-105">You can also guard sensitive information by setting up [Data Loss Prevention](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) (DLP), Azure Information Protection (AIP), [Exchange Online Archiving](https://products.office.com/exchange/microsoft-exchange-online-archiving-email), and also manage your devices in the [Intune portal](#go-to-intune-admin-center).</span></span>

<span data-ttu-id="43295-106">業務を保護するための最も重要な方法の概要については、「 [Microsoft 365 のセキュリティを保護するための10の方法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)」を参照してください。これには、MFA を使用して、2番目のサインインフォームを作成することも含まれます。</span><span class="sxs-lookup"><span data-stu-id="43295-106">See [top 10 ways to secure Microsoft 365 Business plan](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for an overview of the most important ways in which you can protect your business, including using MFA to create a second form of sign-in.</span></span>

<span data-ttu-id="43295-107">簡単に操作する方法については[、「ビジネストレーニングのビデオを保護](https://support.office.com/article/e12187b8-216a-4490-9e3b-df34a06fb787)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43295-107">See [Secure your business training videos](https://support.office.com/article/e12187b8-216a-4490-9e3b-df34a06fb787) for instructions for easy to follow instructions.</span></span>

## <a name="increase-email-malware-protection"></a><span data-ttu-id="43295-108">メールマルウェア対策の向上</span><span class="sxs-lookup"><span data-stu-id="43295-108">Increase email malware protection</span></span>

<span data-ttu-id="43295-109">マルウェアとは、コンピューターまたはネットワークに損害を与える可能性があるソフトウェアで、個人情報や顧客情報などのデータをユーザーから盗むことがあります。</span><span class="sxs-lookup"><span data-stu-id="43295-109">Malware is software that can damage your computers or network, and possibly to steal data from you, including personal or customer information.</span></span> <span data-ttu-id="43295-110">Microsoft 365 Business には、マルウェアに対する保護のベースラインレベルが含まれていますが、追加の設定を設定することで、この保護を強化することができます。</span><span class="sxs-lookup"><span data-stu-id="43295-110">Microsoft 365 Business includes a baseline level of protection against malware, but you can increase this protection by setting up additional settings.</span></span> <span data-ttu-id="43295-111">手順については、「[マルウェア検出トレーニングビデオを有効にする](https://support.office.com/article/02b5783a-eea0-42e8-8856-62440718c3f0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43295-111">See [turn on malware detection](https://support.office.com/article/02b5783a-eea0-42e8-8856-62440718c3f0) training video for instructions.</span></span>

## <a name="set-up-advanced-threat-protection-features"></a><span data-ttu-id="43295-112">高度な脅威保護機能をセットアップする</span><span class="sxs-lookup"><span data-stu-id="43295-112">Set up Advanced Threat Protection features</span></span>

- <span data-ttu-id="43295-113">**安全でない添付ファイルから保護する:** ATP は、仮想環境で電子メールの添付ファイルを開いて、結果の動作の分析を実行することで、悪意のあるコンテンツを特定します。</span><span class="sxs-lookup"><span data-stu-id="43295-113">**Protect against unsafe attachments:** ATP identifies malicious content by opening email attachments in a virtual environment and performing analysis of the resulting behavior.</span></span> <span data-ttu-id="43295-114">コンテンツを評価して、その意図 (通常または悪意) を判断し、ATP が安全でない添付ファイルの配信をブロックすることで、フィッシング詐欺やランサムウェアによる感染から保護します。</span><span class="sxs-lookup"><span data-stu-id="43295-114">The content is evaluated to determine its intent (whether normal or malicious), and ATP blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections.</span></span> <span data-ttu-id="43295-115">添付ファイルの保護を有効にするには、「 [Office 365 ATP の安全な添付ファイルをセットアップ](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775)する」を参照してください。また、悪意のある[ファイルからの保護](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)についての短いトレーニングビデオ</span><span class="sxs-lookup"><span data-stu-id="43295-115">To activate attachment protection, see [set up Office 365 ATP Safe Attachments](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775) help documentation, and [protect against malicious files](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5) short training video.</span></span>
    
- <span data-ttu-id="43295-116">**ユーザーが悪意のあるリンクをクリックしたときに環境を保護します。** また、ATP は、ユーザーがクリックしたときに電子メール内のリンクを調べます。</span><span class="sxs-lookup"><span data-stu-id="43295-116">**Protect your environment when users click malicious links:** ATP also examines links in email at the time a user clicks them.</span></span> <span data-ttu-id="43295-117">リンクが安全でない場合、ユーザーはサイトにアクセスしないように警告が出されるか、サイトがブロックされていることが通知されます。</span><span class="sxs-lookup"><span data-stu-id="43295-117">If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked.</span></span> <span data-ttu-id="43295-118">これにより、フィッシングを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="43295-118">This helps protect against phishing schemes.</span></span> <span data-ttu-id="43295-119">これを有効にするには、「 [Office 365 の ATP 安全](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies)な[](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)リンクの設定」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43295-119">To activate this, see [set up Office 365 ATP Safe Links](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies) help documentation and [protect against malicious sites](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa) short training video.</span></span>

- <span data-ttu-id="43295-120">**お客様の環境をフィッシングから保護します。** ATP のフィッシング対策は、一連の機械学習モデルを受信メッセージに適用して、他のユーザーが既知の情報を抽出して情報を抽出しようとしているフィッシング攻撃からの保護を提供します。情報.</span><span class="sxs-lookup"><span data-stu-id="43295-120">**Protect your enviroment from phishing attempt:**  ATP anti-phishing applies a set of machine learning models together with impersonation detection algorithms to incoming messages to provide protection from phishing attacks where someone is trying to extract information from you by pretending to be a known contact.</span></span> <span data-ttu-id="43295-121">これを有効にするには、「 [ATP のフィッシング対策の](https://docs.microsoft.com/office365/securitycompliance/set-up-anti-phishing-policies)ヘルプドキュメントを設定する」および「[フィッシングからの保護に](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)ついて」の短いトレーニングビデオを参照してください。</span><span class="sxs-lookup"><span data-stu-id="43295-121">To Activate this, see [set up ATP anti-phishing](https://docs.microsoft.com/office365/securitycompliance/set-up-anti-phishing-policies) help documentation and [protect against phishing attempts](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c) short training video.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="43295-122">DLP 機能を設定する</span><span class="sxs-lookup"><span data-stu-id="43295-122">Set up DLP features</span></span>

<span data-ttu-id="43295-123">個人を特定できる情報 (PII) を保護するポリシーを設定する方法の例については、「[テンプレートからの DLP ポリシーの作成](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43295-123">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="43295-124">DLP には、さまざまなロケールに対して、多くの使用可能なポリシーテンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="43295-124">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="43295-125">たとえば、オーストラリアの財務データ、カナダの個人情報法、米国金融データなど。完全なリストについては[、DLP ポリシーテンプレートに含まれるもの](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43295-125">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="43295-126">これらのテンプレートはすべて、PII テンプレートの例と同様に有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="43295-126">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="43295-127">Exchange Online アーカイブを使用したメールの保存期間の設定</span><span class="sxs-lookup"><span data-stu-id="43295-127">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="43295-128">**Exchange Online アーカイブ**ライセンス機能を使用すると、電子情報開示の目的で電子メールコンテンツを保持することで、コンプライアンスおよび規制基準を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="43295-128">**Exchange Online Archiving** license features give you the ability to help maintain compliance and regulatory standards by preserving email content for the purposes of eDiscovery.</span></span> <span data-ttu-id="43295-129">また、訴訟が発生した場合のリスクを軽減し、セキュリティ違反が発生した後や、削除済みアイテムを復元する必要がある場合にも、データを回復することができます。</span><span class="sxs-lookup"><span data-stu-id="43295-129">It also helps reduce your risk in the event of litigation and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="43295-130">これらの機能を有効にするには、訴訟ホールドを使用して、すべてのユーザーのコンテンツを保持するか、アイテム保持ポリシーを使用してカスタマイズを強化できます。</span><span class="sxs-lookup"><span data-stu-id="43295-130">To activate these capabilities, you can use litigation hold to preserve all of a user's content, or use retention policies for greater customization.</span></span> 
  
<span data-ttu-id="43295-131">**訴訟ホールド:** ユーザーのメールボックスを訴訟ホールドの対象にすることで、削除されたアイテムを含むすべてのメールボックスのコンテンツを保持できます。</span><span class="sxs-lookup"><span data-stu-id="43295-131">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="43295-132">メールボックスを訴訟ホールドの対象にするには、管理センターで次のようにします。</span><span class="sxs-lookup"><span data-stu-id="43295-132">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="43295-133">左側のナビゲーションで、[**ユーザー** \> ] [**アクティブなユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="43295-133">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="43295-134">訴訟ホールドの対象とするメールボックスを持つユーザーを選択し、ユーザーウィンドウで [**メールの設定**] を展開し、[**その他の設定**] の横にある [ **Exchange プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="43295-134">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="43295-135">ユーザーのメールボックスページで、左側のナビゲーションにある [\* \* メールボックスの機能] を選択し、[**訴訟ホールド**] の下の [**有効にする**] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="43295-135">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="43295-136">[**訴訟**ホールド] ダイアログボックスで、[**訴訟ホールド期間**] フィールドに訴訟ホールド期間を指定することができます。無限に保持する場合は、フィールドを空のままにします。</span><span class="sxs-lookup"><span data-stu-id="43295-136">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="43295-137">また、メモを追加して、メールボックスの所有者を web サイトに誘導することもできます。 \>これにより、訴訟ホールドの**保存**について詳細に説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43295-137">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="43295-138">**保持:** 保持期間の終了時に、特定の時間だけ保持したり、コンテンツを完全に削除したりするために、カスタマイズされた保持ポリシーを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="43295-138">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="43295-139">詳細については、「[アイテム保持ポリシーの概要](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43295-139">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
## <a name="set-up-azure-information-protection-features"></a><span data-ttu-id="43295-140">Azure Information Protection 機能をセットアップする</span><span class="sxs-lookup"><span data-stu-id="43295-140">Set up Azure Information Protection features</span></span>

<span data-ttu-id="43295-141">Azure Information Protection (AIP) は、組織がラベルを適用することで、ドキュメントや電子メールを分類し、必要に応じて保護できる、クラウドベースのソリューションです。</span><span class="sxs-lookup"><span data-stu-id="43295-141">Azure Information Protection (AIP) is a cloud-based solution that helps an organization to classify and optionally, protect its documents and emails by applying labels.</span></span> <span data-ttu-id="43295-142">ラベルは、ルールと条件を定義する管理者、ユーザーによって手動で、またはユーザーが推奨事項を与える組み合わせによって自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="43295-142">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="43295-143">Web 上の Outlook でメールを送信するときに以下の制限を適用する機能は、すべてのユーザーに対して自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="43295-143">The ability to apply the following restrictions when sending emails in Outlook on the web is automatically enabled for all users:</span></span>
  
- <span data-ttu-id="43295-144">**転送不可**: 受信者はメッセージを読み取ることはできますが、コンテンツを転送、印刷、またはコピーすることはできません</span><span class="sxs-lookup"><span data-stu-id="43295-144">**Do Not Forward**: Recipients can read the message, but they can't forward, print, or copy content</span></span>
    
- <span data-ttu-id="43295-145">**Encrypt**: メッセージ全体が暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="43295-145">**Encrypt**: The entire message is encrypted.</span></span> <span data-ttu-id="43295-146">暗号化されたコンテンツにアクセスする前に、id を確認するために、受信者は特別な手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43295-146">Recipients must take extra steps to confirm their identity before accessing encrypted content and can't remove encryption.</span></span>
    
- <span data-ttu-id="43295-147">**社外秘**: 組織内の従業員に電子メールのコンテンツと添付ファイルへの完全なアクセス許可は付与されますが、組織外のユーザーに対しては含まれません。</span><span class="sxs-lookup"><span data-stu-id="43295-147">**Confidential**: Gives the employees in your organization full permissions to the email content and attachments, but not to people outside your organization.</span></span> <span data-ttu-id="43295-148">データ所有者は、任意の時点でコンテンツを追跡して取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="43295-148">Data owners can track and revoke content at any point.</span></span>
    
- <span data-ttu-id="43295-149">**高機密**: この制限は機密性の高いデータに適用できるため、従業員はデータの表示、編集、および返信を行うことはできませんが、転送、印刷、またはコピーはできません。</span><span class="sxs-lookup"><span data-stu-id="43295-149">**Highly Confidential**: This restriction can be applied to highly confidential data, allowing employees to view, edit, and reply, but not forward, print, or copy the data.</span></span> <span data-ttu-id="43295-150">データ所有者は、任意の時点でコンテンツを追跡して取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="43295-150">Data owners can track and revoke content at any point.</span></span>

### <a name="make-sure-azure-information-protection-is-activated"></a><span data-ttu-id="43295-151">Azure Information Protection がアクティブ化されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="43295-151">Make sure Azure Information Protection is activated</span></span>

<span data-ttu-id="43295-152">AIP がアクティブ化されていることを確認するには</span><span class="sxs-lookup"><span data-stu-id="43295-152">To verify that AIP is activated :</span></span>

1. <span data-ttu-id="43295-153">[Azure portal](https://portal.azure.com/)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="43295-153">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="43295-154">[**すべてのサービス**] を選択し、[**検索] ボックス**に「 *Azure Information Protection* 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="43295-154">Select **All services** and type in *Azure Information Protection* in the **Search Box**.</span></span>

3. <span data-ttu-id="43295-155">結果が表示されたら、 **Azure Information Protection**の横にある [開始] をクリックして、お気に入りにし、後で見つけやすいようにします。</span><span class="sxs-lookup"><span data-stu-id="43295-155">Once the results display, click the start next to **Azure Information Protection** to make it a favorite and easy to find later.</span></span>

4. <span data-ttu-id="43295-156">[ **Azure Information protection** \> **protection activation** ] を選択し、状態が [アクティブ] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="43295-156">Select **Azure Information Protection** \> **Protection activation** and make sure the status is set to activated.</span></span> 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a><span data-ttu-id="43295-157">Azure Information Protection ポリシーと既定のラベルを表示する</span><span class="sxs-lookup"><span data-stu-id="43295-157">View the Azure Information Protection policy and default labels</span></span> 

<span data-ttu-id="43295-158">既存のラベルを表示および変更するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="43295-158">To view, and modify, the existing labels:</span></span>

1. <span data-ttu-id="43295-159">[Azure Information Protection] ダッシュボードで、[**分類** \> **ラベル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="43295-159">On the Azure Information Protection dashboard, select **Classifications** \> **Labels**.</span></span> <br/><span data-ttu-id="43295-160">![Azure Information Protection の標準ラベル。](media/AIPLabels.png)</span><span class="sxs-lookup"><span data-stu-id="43295-160">![Standard labels for Azure Information Protection.](media/AIPLabels.png)</span></span>

2. <span data-ttu-id="43295-161">任意のラベルを選択してオプションを表示したり、表示名や色などを変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="43295-161">You can choose any label to view options, you can change the display name, colors, etc.</span></span>
 
3. <span data-ttu-id="43295-162">独自のラベルを作成する場合は、「[変更して新しいラベルを作成](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43295-162">See  [Modify and create new labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) if you want to create your own.</span></span> 

### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="43295-163">Azure Information Protection クライアントを手動でインストールする</span><span class="sxs-lookup"><span data-stu-id="43295-163">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="43295-164">AIP クライアントを手動でインストールするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="43295-164">To manually install the AIP client:</span></span>

1. <span data-ttu-id="43295-165">[Microsoft ダウンロードセンター](https://www.microsoft.com/download/details.aspx?id=53018)から**Azinfoprotection**をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="43295-165">Download **AzInfoProtection.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="43295-166">Word 文書を表示し、[**ホーム**] タブで [**保護**] オプションが有効になっていることを確認することで、インストールが正常に行われたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="43295-166">You can verify that the installation worked by viewing a Word document and making sure that the **Protect** option is available on the **Home** tab.</span></span> <br/><span data-ttu-id="43295-167">![Word 文書内の [保護] タブのドロップダウン](media/Word_Protect.png)</span><span class="sxs-lookup"><span data-stu-id="43295-167">![Protection tab drop-down in a Word document.](media/Word_Protect.png)</span></span>

<span data-ttu-id="43295-168">詳細については、「[クライアントをインストールする](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43295-168">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>

## <a name="go-to-intune-admin-center"></a><span data-ttu-id="43295-169">Intune 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="43295-169">Go to Intune admin center</span></span>

1. <span data-ttu-id="43295-170">[Azure portal](https://portal.azure.com/)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="43295-170">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="43295-171">[**すべてのサービス**] を選択し、**検索ボックス**に「 *Intune* 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="43295-171">Select **All services** and type in *Intune* in the **Search Box**.</span></span>

3. <span data-ttu-id="43295-172">結果が表示されたら、[ **Microsoft Intune** ] の横にある [開始] をクリックして、お気に入りにし、後で見つけやすいようにします。</span><span class="sxs-lookup"><span data-stu-id="43295-172">Once the results display, click the start next to **Microsoft Intune** to make it a favorite and easy to find later.</span></span>

<span data-ttu-id="43295-173">管理センターに加えて、Intune を使用して組織のデバイスを登録および管理することができます。</span><span class="sxs-lookup"><span data-stu-id="43295-173">In addition to the admin center, you can use Intune to enroll and manage your organization's devices.</span></span> <span data-ttu-id="43295-174">詳細については、「 [Windows デバイスの登録方法](https://docs.microsoft.com/intune/enrollment-method-capabs)」および「 [Intune によって管理されるデバイスの登録オプション](https://docs.microsoft.com/intune/enrollment-options)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43295-174">For more information, see [Capabilities by enrollment method for Windows devices](https://docs.microsoft.com/intune/enrollment-method-capabs) and [Enrollment options for devices managed by Intune](https://docs.microsoft.com/intune/enrollment-options).</span></span>

## <a name="microsoft-secure-score"></a><span data-ttu-id="43295-175">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="43295-175">Microsoft Secure Score</span></span>

