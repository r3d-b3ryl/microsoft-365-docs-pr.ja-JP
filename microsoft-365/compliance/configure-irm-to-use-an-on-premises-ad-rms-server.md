---
title: オンプレミスの AD RMS サーバーを使用するように IRM を構成する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: Active Directory Rights Management Service (EXCHANGE ONLINE RMS) サーバーを使用ADする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c42d793639a9efaf94e3222a172ea192d1e03d3
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227237"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a><span data-ttu-id="afc6d-103">IRM を設定して、オンプレミスの AD RMS サーバーを使用する</span><span class="sxs-lookup"><span data-stu-id="afc6d-103">Configure IRM to use an on-premises AD RMS server</span></span>

<span data-ttu-id="afc6d-104">Exchange Online の Information Rights Management (IRM) は、Exchange Online のオンプレミス展開で使用するために、Windows Server 2008 以降の情報保護テクノロジである Active Directory Rights Management サービス (AD RMS) を使用します。</span><span class="sxs-lookup"><span data-stu-id="afc6d-104">For use with on-premises deployments, Information Rights Management (IRM) in Exchange Online uses Active Directory Rights Management Services (AD RMS), an information protection technology in Windows Server 2008 and later.</span></span> <span data-ttu-id="afc6d-105">IRM 保護を電子メールに適用するには、AD RMS 権利ポリシー テンプレートを電子メール メッセージに適用します。</span><span class="sxs-lookup"><span data-stu-id="afc6d-105">IRM protection is applied to email by applying an AD RMS rights policy template to an email message.</span></span> <span data-ttu-id="afc6d-106">権限はメッセージ自体に添付されているため、オンラインとオフラインの両方、および組織のファイアウォールの内外両方で保護が有効になります。</span><span class="sxs-lookup"><span data-stu-id="afc6d-106">Rights are attached to the message itself so that protection occurs online and offline and inside and outside of your organization's firewall.</span></span>

<span data-ttu-id="afc6d-107">このトピックでは、AD RMS サーバーを使用するように IRM を構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="afc6d-107">This topic shows you how to configure IRM to use an AD RMS server.</span></span> <span data-ttu-id="afc6d-108">Office 365 Message Encryption および Azure Rights Management の新機能の使用Office 365 Message Encryptionについては、「Azure Active Directory FAQ」[をOffice 365 Message Encryptionしてください](./ome-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="afc6d-108">For information about using the new capabilities for Office 365 Message Encryption with Azure Active Directory and Azure Rights Management, see the [Office 365 Message Encryption FAQ](./ome-faq.yml).</span></span>

<span data-ttu-id="afc6d-109">Exchange Online の IRM については、「[Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afc6d-109">To learn more about IRM in Exchange Online, see [Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="afc6d-110">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="afc6d-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="afc6d-111">このタスクの予想所要時間:30 分</span><span class="sxs-lookup"><span data-stu-id="afc6d-111">Estimated time to complete this task: 30 minutes</span></span>

- <span data-ttu-id="afc6d-112">この手順を実行する前に、あらかじめアクセス許可が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="afc6d-112">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="afc6d-113">必要なアクセス許可を確認するには、「メッセージング ポリシーとコンプライアンスのアクセス許可」の「Information Rights Management」 [エントリを参照](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions) してください。</span><span class="sxs-lookup"><span data-stu-id="afc6d-113">To see what permissions you need, see the "Information Rights Management" entry in the [Messaging policy and compliance permissions](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions) topic.</span></span>

- <span data-ttu-id="afc6d-114">AD RMS サーバーは、Windows Server 2008 以降を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="afc6d-114">The AD RMS server must be running Windows Server 2008 or later.</span></span> <span data-ttu-id="afc6d-115">RMS を展開する方法の詳細についてはAD RMS クラスターの [インストールAD参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="afc6d-115">For details about how to deploy AD RMS, see [Installing an AD RMS Cluster](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11)).</span></span>

- <span data-ttu-id="afc6d-116">Windows PowerShell のインストール方法と構成方法、およびサービスへの接続方法については、「[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afc6d-116">For details about how to install and configure Windows PowerShell and connect to the service, see [Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="afc6d-117">このトピックの手順に適用されるキーボード ショートカットの詳細については、「Exchange 管理センターのキーボード ショートカット」を[参照](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="afc6d-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="afc6d-p105">問題がある場合は、Exchange のフォーラムで質問してください。 次のフォーラムにアクセスしてください。[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)、 または [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="afc6d-p105">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span>

## <a name="how-do-you-do-this"></a><span data-ttu-id="afc6d-121">実行方法</span><span class="sxs-lookup"><span data-stu-id="afc6d-121">How do you do this?</span></span>
<span data-ttu-id="afc6d-122"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="afc6d-122"><a name="sectionSection1"> </a></span></span>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a><span data-ttu-id="afc6d-123">手順 1:AD RMS コンソールを使用して、AD RMS サーバーから信頼された発行ドメイン (TPD) をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="afc6d-123">Step 1: Use the AD RMS console to export a trusted publishing domain (TPD) from an AD RMS server</span></span>

<span data-ttu-id="afc6d-p106">まず、信頼された発行ドメイン (TPD) を社内 AD RMS サーバーから XML ファイルにエクスポートします。TPD には RMS 機能を使用するために必要な以下の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="afc6d-p106">The first step is to export a trusted publishing domain (TPD) from the on-premises AD RMS server to an XML file. The TPD contains the following settings needed to use RMS features:</span></span>

- <span data-ttu-id="afc6d-126">証明書とライセンスの署名と暗号化に使用されるサーバー ライセンサー証明書 (SLC)</span><span class="sxs-lookup"><span data-stu-id="afc6d-126">The server licensor certificate (SLC) used for signing and encrypting certificates and licenses</span></span>

- <span data-ttu-id="afc6d-127">ライセンスと発行に使用される URL</span><span class="sxs-lookup"><span data-stu-id="afc6d-127">The URLs used for licensing and publishing</span></span>

- <span data-ttu-id="afc6d-128">TPD に固有の SLC を使用して作成された AD RMS 権利ポリシー テンプレート</span><span class="sxs-lookup"><span data-stu-id="afc6d-128">The AD RMS rights policy templates that were created with the specific SLC for that TPD</span></span>

<span data-ttu-id="afc6d-129">TPD をインポートすると、その TPD はストレージに保存され、保護Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="afc6d-129">When you import the TPD, it's stored and protected in Exchange Online.</span></span>

1. <span data-ttu-id="afc6d-130">Active Directory Rights Management サービスのコンソールを開いて、AD RMS クラスターを展開します。</span><span class="sxs-lookup"><span data-stu-id="afc6d-130">Open the Active Directory Rights Management Services console, and then expand the AD RMS cluster.</span></span>

2. <span data-ttu-id="afc6d-131">コンソール ツリーで、**[信頼ポリシー]** を展開してから、**[信頼された発行ドメイン]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="afc6d-131">In the console tree, expand **Trust Policies**, and then click **Trusted Publishing Domains**.</span></span>

3. <span data-ttu-id="afc6d-132">結果ウィンドウで、エクスポートするドメインの証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="afc6d-132">In the results pane, select the certificate for the domain you want to export.</span></span>

4. <span data-ttu-id="afc6d-133">**[操作]** ウィンドウで、**[信頼された発行ドメインのエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="afc6d-133">In the **Actions** pane, click **Export Trusted Publishing Domain**.</span></span>

5. <span data-ttu-id="afc6d-134">**[発行ドメイン ファイル]** の **[名前を付けて保存]** をクリックして、ローカル コンピューター上の特定の場所にファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="afc6d-134">In the **Publishing domain file** box, click **Save As** to save the file to a specific location on the local computer.</span></span> <span data-ttu-id="afc6d-135">ファイル名を入力し、ファイル名の拡張子を必ず指定し、[  `.xml` 保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="afc6d-135">Type a file name, making sure to specify the  `.xml` file name extension, and then click **Save**.</span></span>

6. <span data-ttu-id="afc6d-p108">**[パスワード]** ボックスと **[パスワードの確認入力]** ボックスに、信頼された発行ドメイン ファイルの暗号化に使用する強力なパスワードを入力します。このパスワードは、クラウドベースの電子メール組織に TPD をインポートするときに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afc6d-p108">In the **Password** and **Confirm Password** boxes, type a strong password that will be used to encrypt the trusted publishing domain file. You will have to specify this password when you import the TPD to your cloud-based email organization.</span></span>

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a><span data-ttu-id="afc6d-138">手順 2: 管理シェルExchange使用して、TPD をインポートして管理Exchange Online</span><span class="sxs-lookup"><span data-stu-id="afc6d-138">Step 2: Use the Exchange Management Shell to import the TPD to Exchange Online</span></span>

<span data-ttu-id="afc6d-p109">TPD を XML ファイルにエクスポートした後は、TPD を Exchange Online にインポートする必要があります。TPD をインポートすると、組織の AD RM テンプレートもインポートされます。最初の TPD をインポートすると、それがクラウドベース組織の既定の TPD になります。別の TPD をインポートする場合は、**Default** スイッチを使用してこの TPD を既定の TPD にし、ユーザーが使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="afc6d-p109">After the TPD is exported to an XML file, you have to import it to Exchange Online. When a TPD is imported, your organization's AD RMS templates are also imported. When the first TPD is imported, it becomes the default TPD for your cloud-based organization. If you import another TPD, you can use the **Default** switch to make it the default TPD that is available to users.</span></span>

<span data-ttu-id="afc6d-143">TPD をインポートするには、Windows PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="afc6d-143">To import the TPD, run the following command in Windows PowerShell:</span></span>

```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

<span data-ttu-id="afc6d-144">_ExtranetLicensingUrl_ パラメーターと _イントラネットLicensingUrl_ パラメーターの値は、コンソールActive Directory Rights Management サービスできます。</span><span class="sxs-lookup"><span data-stu-id="afc6d-144">You can obtain the values for the  _ExtranetLicensingUrl_ and  _IntranetLicensingUrl_ parameters in the Active Directory Rights Management Services console.</span></span> <span data-ttu-id="afc6d-145">コンソール ツリーで AD RMS クラスターを選択します。</span><span class="sxs-lookup"><span data-stu-id="afc6d-145">Select the AD RMS cluster in the console tree.</span></span> <span data-ttu-id="afc6d-146">ライセンスの URL が結果ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="afc6d-146">The licensing URLs are displayed in the results pane.</span></span> <span data-ttu-id="afc6d-147">コンテンツを復号化する必要がある場合と使用する TPD を Exchange Online で決定する必要がある場合は、これらの URL が電子メール クライアントによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="afc6d-147">These URLs are used by email clients when content has to be decrypted and when Exchange Online needs to determine which TPD to use.</span></span>

<span data-ttu-id="afc6d-148">このコマンドを実行すると、パスワードの入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="afc6d-148">When you run this command, you'll be prompted for a password.</span></span> <span data-ttu-id="afc6d-149">TPD を AD RMS サーバーからエクスポートしたときに指定したパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="afc6d-149">Enter the password that you specified when you exported the TPD from your AD RMS server.</span></span>

<span data-ttu-id="afc6d-p112">たとえば、次のコマンドは、AD RMS サーバーからエクスポートして管理者アカウントのデスクトップに保存された XML ファイルを使用して、Exported TPD という名前の TPD をインポートします。Name パラメーターは TPD の名前を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="afc6d-p112">For example, the following command imports the TPD named Exported TPD using the XML file that you exported from your AD RMS server and saved to the desktop of the Administrator account. The Name parameter is used to specify a name to the TPD.</span></span>

```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

<span data-ttu-id="afc6d-152">構文およびパラメーターの詳細については、「[Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afc6d-152">For detailed syntax and parameter information, see [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain).</span></span>

#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="afc6d-153">このステップの検証方法</span><span class="sxs-lookup"><span data-stu-id="afc6d-153">How do you know this step worked?</span></span>

<span data-ttu-id="afc6d-154">TPD が正常にインポートされたことを確認するには **、Get-RMSTrustedPublishingDomain** コマンドレットを実行して、組織の TPD をExchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="afc6d-154">To verify that you have successfully imported the TPD, run the **Get-RMSTrustedPublishingDomain** cmdlet to retrieve TPDs in your Exchange Online organization.</span></span> <span data-ttu-id="afc6d-155">詳細については、「[Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain)」内の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afc6d-155">For details, see the examples in [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain).</span></span>

### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a><span data-ttu-id="afc6d-156">手順 3: 管理シェルを使用Exchange RMS 権限ポリシー テンプレートAD配布する</span><span class="sxs-lookup"><span data-stu-id="afc6d-156">Step 3: Use the Exchange Management Shell to distribute an AD RMS rights policy template</span></span>

<span data-ttu-id="afc6d-157">TPD をインポートしたら、AD RMS 権利ポリシー テンプレートが配布されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afc6d-157">After you import the TPD, you must make sure an AD RMS rights policy template is distributed.</span></span> <span data-ttu-id="afc6d-158">分散テンプレートは、Outlook on the web (以前は Outlook Web App) ユーザーに表示され、電子メール メッセージにテンプレートを適用できます。</span><span class="sxs-lookup"><span data-stu-id="afc6d-158">A distributed template is visible to Outlook on the web (formerly known as Outlook Web App) users, who can then apply the templates to an email message.</span></span>

<span data-ttu-id="afc6d-159">既定の TPD に含まれているすべてのテンプレートの一覧を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="afc6d-159">To return a list of all templates contained in the default TPD, run the following command:</span></span>

```powershell
Get-RMSTemplate -Type All | fl
```

<span data-ttu-id="afc6d-160">Type パラメーターの値  _が指定_ されている  `Archived` 場合、テンプレートはユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="afc6d-160">If the value of the  _Type_ parameter is  `Archived`, the template isn't visible to users.</span></span> <span data-ttu-id="afc6d-161">既定の TPD 内の分散テンプレートだけが、既定の TPD でOutlook on the web。</span><span class="sxs-lookup"><span data-stu-id="afc6d-161">Only distributed templates in the default TPD are available in Outlook on the web.</span></span>

<span data-ttu-id="afc6d-162">テンプレートを配布するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="afc6d-162">To distribute a template, run the following command:</span></span>

```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

<span data-ttu-id="afc6d-163">たとえば、次のコマンドは、Company Confidential テンプレートをインポートします。</span><span class="sxs-lookup"><span data-stu-id="afc6d-163">For example, the following command imports the Company Confidential template.</span></span>

```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

<span data-ttu-id="afc6d-164">構文とパラメーターの詳細については、「[Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate)」と「[Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afc6d-164">For detailed syntax and parameter information, see [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) and [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate).</span></span>

<span data-ttu-id="afc6d-165">**転送不可テンプレート**</span><span class="sxs-lookup"><span data-stu-id="afc6d-165">**The Do Not Forward template**</span></span>

<span data-ttu-id="afc6d-p116">既定の TPD を社内組織から Exchange Online にインポートすると、**Do Not Forward** という名前の AD RMS 権利ポリシー テンプレートが 1 つインポートされます。既定で、このテンプレートは、既定の TPD をインポートしたときに配布されます。**Set-RMSTemplate** コマンドレットを使用して **Do Not Forward** テンプレートを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="afc6d-p116">When you import the default TPD from your on-premises organization into Exchange Online, one AD RMS rights policy template named **Do Not Forward** is imported. By default, this template is distributed when you import the default TPD. You can't use the **Set-RMSTemplate** cmdlet to modify the **Do Not Forward** template.</span></span>

<span data-ttu-id="afc6d-p117">**Do Not Forward** テンプレートがメッセージに適用されている場合は、メッセージにアドレスが指定された受信者のみがメッセージを読むことができます。受信者が次の操作を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="afc6d-p117">When the **Do Not Forward** template is applied to a message, only the recipients addressed in the message can read the message. Additionally, recipients can't do the following:</span></span>

- <span data-ttu-id="afc6d-171">メッセージを別のユーザーに転送する。</span><span class="sxs-lookup"><span data-stu-id="afc6d-171">Forward the message to another person.</span></span>

- <span data-ttu-id="afc6d-172">メッセージの内容をコピーする。</span><span class="sxs-lookup"><span data-stu-id="afc6d-172">Copy content from the message.</span></span>

- <span data-ttu-id="afc6d-173">メッセージを印刷する。</span><span class="sxs-lookup"><span data-stu-id="afc6d-173">Print the message.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="afc6d-174">**Do Not Forward** テンプレートは、サードパーティのスクリーン キャプチャ プログラムやカメラを使用してメッセージ内の情報がコピーされたり、ユーザーによって情報が書き写されるのを防げるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="afc6d-174">The **Do Not Forward** template can't prevent information in a message from being copied with third-party screen capture programs, cameras, or users manually transcribing the information</span></span>

<span data-ttu-id="afc6d-p118">IRM 保護要件に合わせて、社内組織内の AD RMS サーバー上に追加の AD RMS 権利ポリシー テンプレートを作成できます。追加の AD RMS 権利ポリシー テンプレートを作成する場合は、TPD を社内 AD RMS サーバーから再びエクスポートして、クラウドベースの電子メール組織の TPD を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afc6d-p118">You can create additional AD RMS rights policy templates on the AD RMS server in your on-premises organization to meet your IRM protection requirements. If you create additional AD RMS rights policy templates, you have to export the TPD from the on-premises AD RMS server again and refresh the TPD in the cloud-based email organization.</span></span>

#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="afc6d-177">このステップの検証方法</span><span class="sxs-lookup"><span data-stu-id="afc6d-177">How do you know this step worked?</span></span>

<span data-ttu-id="afc6d-178">RMS 権限ポリシー テンプレートが正常に配布AD確認するには **、Get-RMSTemplate** コマンドレットを実行してテンプレートのプロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="afc6d-178">To verify that you have successfully distributed and AD RMS rights policy template, run the **Get-RMSTemplate** cmdlet to check the template's properties.</span></span> <span data-ttu-id="afc6d-179">詳細については、「[Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate)」内の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afc6d-179">For details, see the examples in [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate).</span></span>

### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a><span data-ttu-id="afc6d-180">手順 4: IRM を有効Exchange管理シェルを使用する</span><span class="sxs-lookup"><span data-stu-id="afc6d-180">Step 4: Use the Exchange Management Shell to enable IRM</span></span>

<span data-ttu-id="afc6d-181">TPD をインポートして AD RMS 権利ポリシー テンプレートを配布したら、次のコマンドを実行して、クラウドベースの電子メール組織に対して IRM を有効にします。</span><span class="sxs-lookup"><span data-stu-id="afc6d-181">After you import the TPD and distribute an AD RMS rights policy template, run the following command to enable IRM for your cloud-based email organization.</span></span>

```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

<span data-ttu-id="afc6d-182">構文およびパラメーターの詳細については、「[Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afc6d-182">For detailed syntax and parameter information, see [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration).</span></span>

#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="afc6d-183">このステップの検証方法</span><span class="sxs-lookup"><span data-stu-id="afc6d-183">How do you know this step worked?</span></span>

<span data-ttu-id="afc6d-184">IRM が正常に有効にされたことを確認するには[、Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration)コマンドレットを実行して、組織の IRM 構成Exchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="afc6d-184">To verify that you have successfully enabled IRM, run the [Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) cmdlet to check IRM configuration in the Exchange Online organization.</span></span>

## <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="afc6d-185">このタスクの検証方法</span><span class="sxs-lookup"><span data-stu-id="afc6d-185">How do you know this task worked?</span></span>
<span data-ttu-id="afc6d-186"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="afc6d-186"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="afc6d-187">TPD が正常にインポートされ、IRM が有効になったことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="afc6d-187">To verify that you have successfully imported the TPD and enabled IRM, do the following:</span></span>

- <span data-ttu-id="afc6d-188">IRM の機能をテストするには、**Test-IRMConfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="afc6d-188">Use the **Test-IRMConfiguration** cmdlet to test IRM functionality.</span></span> <span data-ttu-id="afc6d-189">詳細については [、「Test-IRMConfiguration」の「例 1」を参照してください](/powershell/module/exchange/test-irmconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="afc6d-189">For details, see "Example 1" in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).</span></span>

- <span data-ttu-id="afc6d-190">拡張メニュー (その他のOutlook on the webアイコン) から [アクセス許可の設定] オプションを選択して、新しいメッセージを作成し、IRM-protect ![ します ](../media/ITPro-EAC-MoreOptionsIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="afc6d-190">Compose a new message in Outlook on the web and IRM-protect it by selecting **Set permissions** option from the extended menu (![More Options Icon](../media/ITPro-EAC-MoreOptionsIcon.gif)).</span></span>
