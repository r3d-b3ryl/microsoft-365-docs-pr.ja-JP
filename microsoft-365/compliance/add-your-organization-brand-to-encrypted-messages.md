---
title: 暗号化されたメッセージに組織ブランドを追加する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: グローバル管理者Office 365、暗号化ポータルのコンテンツに暗号化された電子メール メッセージに組織&を適用する方法について学習します。
ms.openlocfilehash: 95320e9f268f19cedd993efe4fa0e68fd75af125
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430734"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a><span data-ttu-id="300fc-103">組織のブランドをビジネス メッセージ暗号化Microsoft 365メッセージに追加する</span><span class="sxs-lookup"><span data-stu-id="300fc-103">Add your organization's brand to your Microsoft 365 for business Message Encryption encrypted messages</span></span>

<span data-ttu-id="300fc-104">会社のブランド化を適用して、組織の電子メール メッセージと暗号化ポータルの外観をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="300fc-104">You can apply your company branding to customize the look of your organization's email messages and the encryption portal.</span></span> <span data-ttu-id="300fc-105">作業を始める前に、グローバル管理者のアクセス許可を仕事または学校のアカウントに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="300fc-105">You'll need to apply global administrator permissions to your work or school account before you can get started.</span></span> <span data-ttu-id="300fc-106">これらのアクセス許可を取得したら、Get-OMEConfigurationおよびSet-OMEConfiguration Windows PowerShellコマンドレットを使用して、暗号化された電子メール メッセージの次の部分をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="300fc-106">Once you have these permissions, use the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets to customize these parts of encrypted email messages:</span></span>
  
- <span data-ttu-id="300fc-107">入門テキスト</span><span class="sxs-lookup"><span data-stu-id="300fc-107">Introductory text</span></span>

- <span data-ttu-id="300fc-108">免責事項のテキスト</span><span class="sxs-lookup"><span data-stu-id="300fc-108">Disclaimer text</span></span>

- <span data-ttu-id="300fc-109">組織のプライバシーに関する声明の URL</span><span class="sxs-lookup"><span data-stu-id="300fc-109">URL for Your organization's privacy statement</span></span>

- <span data-ttu-id="300fc-110">OME ポータルのテキスト</span><span class="sxs-lookup"><span data-stu-id="300fc-110">Text in the OME portal</span></span>

- <span data-ttu-id="300fc-111">電子メール メッセージと OME ポータルに表示されるロゴ、またはロゴを使用するかどうか</span><span class="sxs-lookup"><span data-stu-id="300fc-111">Logo that appears in the email message and OME portal, or whether to use a logo at all</span></span>

- <span data-ttu-id="300fc-112">電子メール メッセージと OME ポータルの背景色</span><span class="sxs-lookup"><span data-stu-id="300fc-112">Background color in the email message and OME portal</span></span>

<span data-ttu-id="300fc-113">いつでも既定のルック アンド フィールに戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="300fc-113">You can also revert back to the default look and feel at any time.</span></span>

<span data-ttu-id="300fc-114">より詳細な制御が必要な場合は、Office 365 Advanced Message Encryptionを使用して、組織から送信される暗号化された電子メール用の複数のテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="300fc-114">If you'd like more control, use Office 365 Advanced Message Encryption to create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="300fc-115">これらのテンプレートを使用して、エンド ユーザー エクスペリエンスの一部を制御します。</span><span class="sxs-lookup"><span data-stu-id="300fc-115">Use these templates to control parts of the end-user experience.</span></span> <span data-ttu-id="300fc-116">たとえば、受信者が Google、Yahoo、Microsoft アカウントを使用して暗号化ポータルにサインインできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="300fc-116">For example, specify whether recipients can use Google, Yahoo, and Microsoft Accounts to sign in to the encryption portal.</span></span> <span data-ttu-id="300fc-117">テンプレートを使用して、次のようないくつかの使用例を満たします。</span><span class="sxs-lookup"><span data-stu-id="300fc-117">Use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="300fc-118">財務、営業など、個々の部署。</span><span class="sxs-lookup"><span data-stu-id="300fc-118">Individual departments, such as Finance, Sales, and so on.</span></span>

- <span data-ttu-id="300fc-119">異なる製品</span><span class="sxs-lookup"><span data-stu-id="300fc-119">Different products</span></span>

- <span data-ttu-id="300fc-120">地理的な地域や国が異なる</span><span class="sxs-lookup"><span data-stu-id="300fc-120">Different geographical regions or countries</span></span>

- <span data-ttu-id="300fc-121">電子メールの取り消しを許可するかどうか</span><span class="sxs-lookup"><span data-stu-id="300fc-121">Whether you want to allow emails to be revoked</span></span>

- <span data-ttu-id="300fc-122">指定した日数を過ぎると、外部の受信者に送信されるメールの有効期限が切れるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="300fc-122">Whether you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="300fc-123">テンプレートを作成したら、メール フロー ルールを使用して、暗号化されたExchange適用できます。</span><span class="sxs-lookup"><span data-stu-id="300fc-123">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="300fc-124">このテンプレートをOffice 365 Advanced Message Encryption、これらのテンプレートを使用してブランド化したメールを取り消します。</span><span class="sxs-lookup"><span data-stu-id="300fc-124">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>

## <a name="work-with-ome-branding-templates"></a><span data-ttu-id="300fc-125">OME ブランド テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="300fc-125">Work with OME branding templates</span></span>

<span data-ttu-id="300fc-126">ブランド 化テンプレート内の複数の機能を変更できます。</span><span class="sxs-lookup"><span data-stu-id="300fc-126">You can modify several features within a branding template.</span></span> <span data-ttu-id="300fc-127">既定のテンプレートは変更できますが、削除は行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="300fc-127">You can modify, but not remove, the default template.</span></span> <span data-ttu-id="300fc-128">高度なメッセージ暗号化を使用している場合は、カスタム テンプレートを作成、変更、および削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="300fc-128">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span> <span data-ttu-id="300fc-129">このWindows PowerShellを使用して、一度に 1 つのブランド 化テンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="300fc-129">Use Windows PowerShell to work with one branding template at a time.</span></span>

- <span data-ttu-id="300fc-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - 作成した既定のブランド テンプレートまたはカスタム ブランド テンプレートを変更します。</span><span class="sxs-lookup"><span data-stu-id="300fc-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - Modify the default branding template or a custom branding template that you created.</span></span>
- <span data-ttu-id="300fc-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - 新しいブランド テンプレートを作成します。高度なメッセージ暗号化のみ。</span><span class="sxs-lookup"><span data-stu-id="300fc-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - Create a new branding template, Advanced Message Encryption only.</span></span>
- <span data-ttu-id="300fc-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - カスタム ブランド テンプレートの削除、高度なメッセージ暗号化のみ。</span><span class="sxs-lookup"><span data-stu-id="300fc-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - Remove a custom branding template, Advanced Message Encryption only.</span></span> <span data-ttu-id="300fc-133">既定のブランド 化テンプレートは削除できない。</span><span class="sxs-lookup"><span data-stu-id="300fc-133">You can't delete the default branding template.</span></span>
  
## <a name="modify-an-ome-branding-template"></a><span data-ttu-id="300fc-134">OME ブランド テンプレートの変更</span><span class="sxs-lookup"><span data-stu-id="300fc-134">Modify an OME branding template</span></span>

<span data-ttu-id="300fc-135">ブランドWindows PowerShell一度に 1 つのブランド テンプレートを変更するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="300fc-135">Use Windows PowerShell to modify one branding template at a time.</span></span> <span data-ttu-id="300fc-136">高度なメッセージ暗号化を使用している場合は、カスタム テンプレートを作成、変更、および削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="300fc-136">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span>

1. <span data-ttu-id="300fc-137">組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="300fc-137">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="300fc-138">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="300fc-138">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="300fc-139">[Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration)の説明に従って、Set-OMEConfigurationコマンドレットを使用するか、ガイダンスとして次の図と表を使用します。</span><span class="sxs-lookup"><span data-stu-id="300fc-139">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) or use the following graphic and table for guidance.</span></span>

![カスタマイズ可能な電子メール パーツ](../media/ome-template-breakout.png)

|<span data-ttu-id="300fc-141">**カスタマイズする暗号化エクスペリエンスの特性**</span><span class="sxs-lookup"><span data-stu-id="300fc-141">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="300fc-142">**次のコマンドを使用する**</span><span class="sxs-lookup"><span data-stu-id="300fc-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="300fc-143">背景色</span><span class="sxs-lookup"><span data-stu-id="300fc-143">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> <span data-ttu-id="300fc-144">**例:**</span><span class="sxs-lookup"><span data-stu-id="300fc-144">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> <span data-ttu-id="300fc-145">背景色の詳細については、この記事の後半の [「背景色](#background-color-reference) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="300fc-145">For more information about background colors, see the [Background colors](#background-color-reference) section later in this article.</span></span>|
|<span data-ttu-id="300fc-146">ロゴ</span><span class="sxs-lookup"><span data-stu-id="300fc-146">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> <span data-ttu-id="300fc-147">**例:**</span><span class="sxs-lookup"><span data-stu-id="300fc-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="300fc-148">サポートされているファイル形式: .png、.jpg、.bmp、.tiff</span><span class="sxs-lookup"><span data-stu-id="300fc-148">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="300fc-149">ロゴ ファイルの最適なサイズ:40 KB 未満</span><span class="sxs-lookup"><span data-stu-id="300fc-149">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="300fc-150">ロゴ画像の最適なサイズ: 170x70 ピクセル。</span><span class="sxs-lookup"><span data-stu-id="300fc-150">Optimal size of logo image: 170x70 pixels.</span></span> <span data-ttu-id="300fc-151">画像がこれらのサイズを超えた場合、サービスはポータルに表示するロゴのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="300fc-151">If your image exceeds these dimensions, the service resizes your logo for display in the portal.</span></span> <span data-ttu-id="300fc-152">サービスはグラフィック ファイル自体を変更しません。</span><span class="sxs-lookup"><span data-stu-id="300fc-152">The service doesn't modify the graphic file itself.</span></span> <span data-ttu-id="300fc-153">最適な結果を得る場合は、最適なサイズを使用します。</span><span class="sxs-lookup"><span data-stu-id="300fc-153">For best results, use the optimal size.</span></span>|
|<span data-ttu-id="300fc-154">送信者の名前とメール アドレスの横にあるテキスト</span><span class="sxs-lookup"><span data-stu-id="300fc-154">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="300fc-155">**例:**</span><span class="sxs-lookup"><span data-stu-id="300fc-155">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="300fc-156">[メッセージの読み取り] ボタンに表示されるテキスト</span><span class="sxs-lookup"><span data-stu-id="300fc-156">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="300fc-157">**例:**</span><span class="sxs-lookup"><span data-stu-id="300fc-157">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="300fc-158">[メッセージの読み取り] ボタンの下に表示されるテキスト</span><span class="sxs-lookup"><span data-stu-id="300fc-158">Text that appears below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="300fc-159">**例:**</span><span class="sxs-lookup"><span data-stu-id="300fc-159">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="300fc-160">[プライバシーに関する声明] リンクの URL</span><span class="sxs-lookup"><span data-stu-id="300fc-160">URL for the Privacy Statement link</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> <span data-ttu-id="300fc-161">**例:**</span><span class="sxs-lookup"><span data-stu-id="300fc-161">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|<span data-ttu-id="300fc-162">暗号化メッセージを含む電子メールの免責文</span><span class="sxs-lookup"><span data-stu-id="300fc-162">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="300fc-163">**例:**</span><span class="sxs-lookup"><span data-stu-id="300fc-163">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="300fc-164">暗号化メールの表示ポータルの最上部に表示されるテキスト</span><span class="sxs-lookup"><span data-stu-id="300fc-164">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="300fc-165">**例:**</span><span class="sxs-lookup"><span data-stu-id="300fc-165">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="300fc-166">このカスタム テンプレートのワンタイム パス コードを使用して認証を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="300fc-166">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="300fc-167">**例:**</span><span class="sxs-lookup"><span data-stu-id="300fc-167">**Examples:**</span></span> <br/><span data-ttu-id="300fc-168">このカスタム テンプレートでワンタイム パスコードを有効にするには</span><span class="sxs-lookup"><span data-stu-id="300fc-168">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="300fc-169">このカスタム テンプレートのワンタイム パスコードを無効にするには</span><span class="sxs-lookup"><span data-stu-id="300fc-169">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="300fc-170">このカスタム テンプレートの Microsoft、Google、Yahoo ID を使用して認証を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="300fc-170">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="300fc-171">**例:**</span><span class="sxs-lookup"><span data-stu-id="300fc-171">**Examples:**</span></span> <br/><span data-ttu-id="300fc-172">このカスタム テンプレートのソーシャル ID を有効にするには</span><span class="sxs-lookup"><span data-stu-id="300fc-172">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="300fc-173">このカスタム テンプレートのソーシャル ID を無効にするには</span><span class="sxs-lookup"><span data-stu-id="300fc-173">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a><span data-ttu-id="300fc-174">OME ブランド テンプレートの作成 (高度なメッセージ暗号化)</span><span class="sxs-lookup"><span data-stu-id="300fc-174">Create an OME branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="300fc-175">このコマンドレットを[Office 365 Advanced Message Encryption、New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration)コマンドレットを使用して、組織のカスタム ブランド 化テンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="300fc-175">If you have Office 365 Advanced Message Encryption, you can create custom branding templates for your organization by using the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet.</span></span> <span data-ttu-id="300fc-176">テンプレートを作成したら、「OME ブランド テンプレートの変更」の説明に従って、Set-OMEConfiguration コマンドレットを使用してテンプレート [を変更します](#modify-an-ome-branding-template)。</span><span class="sxs-lookup"><span data-stu-id="300fc-176">Once you've created the template, you modify the template by using the Set-OMEConfiguration cmdlet as described in [Modify an OME branding template](#modify-an-ome-branding-template).</span></span> <span data-ttu-id="300fc-177">複数のテンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="300fc-177">You can create multiple templates.</span></span>

<span data-ttu-id="300fc-178">新しいカスタム ブランド テンプレートを作成するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="300fc-178">To create a new custom branding template:</span></span>

1. <span data-ttu-id="300fc-179">組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="300fc-179">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="300fc-180">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="300fc-180">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="300fc-181">[New-OMEConfiguration コマンドレットを使用して](/powershell/module/exchange/new-omeconfiguration)、新しいテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="300fc-181">Use the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   <span data-ttu-id="300fc-182">例えば、</span><span class="sxs-lookup"><span data-stu-id="300fc-182">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a><span data-ttu-id="300fc-183">既定のブランド 化テンプレートを元の値に戻す</span><span class="sxs-lookup"><span data-stu-id="300fc-183">Return the default branding template to its original values</span></span>

<span data-ttu-id="300fc-184">ブランドのカスタマイズなど、既定のテンプレートからすべての変更を削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="300fc-184">To remove all modifications from the default template, including brand customizations, and so on, complete these steps:</span></span>
  
1. <span data-ttu-id="300fc-185">組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="300fc-185">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="300fc-186">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="300fc-186">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="300fc-187">**Set-OMEConfiguration** の説明に従って [、Set-OMEConfiguration コマンドレットを使用します](/powershell/module/exchange/Set-OMEConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="300fc-187">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration).</span></span> <span data-ttu-id="300fc-188">DisclaimerText、EmailText、PortalText の各値から組織のブランド化されたカスタマイズを削除するには、値を空の文字列に設定します `""` 。</span><span class="sxs-lookup"><span data-stu-id="300fc-188">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string, `""`.</span></span> <span data-ttu-id="300fc-189">Logo などのすべての画像値に対して、値をに設定します  `"$null"` 。</span><span class="sxs-lookup"><span data-stu-id="300fc-189">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="300fc-190">次の表では、暗号化カスタマイズ オプションの既定値について説明します。</span><span class="sxs-lookup"><span data-stu-id="300fc-190">The following table describes the encryption customization option defaults.</span></span>

   |<span data-ttu-id="300fc-191">この暗号化の機能を既定のテキストと画像に戻すには</span><span class="sxs-lookup"><span data-stu-id="300fc-191">To revert this feature of the encryption experience back to the default text and image</span></span>|<span data-ttu-id="300fc-192">次のコマンドを使用する</span><span class="sxs-lookup"><span data-stu-id="300fc-192">Use these commands</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="300fc-193">暗号化された電子メール メッセージに付属する既定のテキスト。</span><span class="sxs-lookup"><span data-stu-id="300fc-193">Default text that comes with encrypted email messages.</span></span>  <span data-ttu-id="300fc-194">暗号化メッセージの表示手順の上に表示される既定のテキスト</span><span class="sxs-lookup"><span data-stu-id="300fc-194">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> <span data-ttu-id="300fc-195">**例:**</span><span class="sxs-lookup"><span data-stu-id="300fc-195">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |<span data-ttu-id="300fc-196">暗号化メッセージを含む電子メールの免責文</span><span class="sxs-lookup"><span data-stu-id="300fc-196">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> <span data-ttu-id="300fc-197">**例:**</span><span class="sxs-lookup"><span data-stu-id="300fc-197">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |<span data-ttu-id="300fc-198">暗号化メールの表示ポータルの最上部に表示されるテキスト</span><span class="sxs-lookup"><span data-stu-id="300fc-198">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> <span data-ttu-id="300fc-199">**既定に戻す例:**</span><span class="sxs-lookup"><span data-stu-id="300fc-199">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |<span data-ttu-id="300fc-200">ロゴ</span><span class="sxs-lookup"><span data-stu-id="300fc-200">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> <span data-ttu-id="300fc-201">**既定に戻す例:**</span><span class="sxs-lookup"><span data-stu-id="300fc-201">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |<span data-ttu-id="300fc-202">背景色</span><span class="sxs-lookup"><span data-stu-id="300fc-202">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> <span data-ttu-id="300fc-203">**既定に戻す例:**</span><span class="sxs-lookup"><span data-stu-id="300fc-203">**Example reverting back to default:**</span></span> <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a><span data-ttu-id="300fc-204">カスタム ブランド テンプレートを削除する (高度なメッセージ暗号化)</span><span class="sxs-lookup"><span data-stu-id="300fc-204">Remove a custom branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="300fc-205">削除または削除できるのは、作成したブランド 化テンプレートのみです。</span><span class="sxs-lookup"><span data-stu-id="300fc-205">You can only remove or delete branding templates that you've made.</span></span> <span data-ttu-id="300fc-206">既定のブランド 化テンプレートを削除できない。</span><span class="sxs-lookup"><span data-stu-id="300fc-206">You can't remove the default branding template.</span></span>

<span data-ttu-id="300fc-207">カスタム ブランド テンプレートを削除するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="300fc-207">To remove a custom branding template:</span></span>
  
1. <span data-ttu-id="300fc-208">組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="300fc-208">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="300fc-209">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="300fc-209">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="300fc-210">次のように **Remove-OMEConfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="300fc-210">Use the **Remove-OMEConfiguration** cmdlet as follows:</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   <span data-ttu-id="300fc-211">例えば、</span><span class="sxs-lookup"><span data-stu-id="300fc-211">For example,</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   <span data-ttu-id="300fc-212">詳細については [、「Remove-OMEConfiguration」を参照してください](/powershell/module/exchange/remove-omeconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="300fc-212">For more information, see [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration).</span></span>

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a><span data-ttu-id="300fc-213">カスタム ブランドExchange暗号化されたメールに適用するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="300fc-213">Create an Exchange mail flow rule that applies your custom branding to encrypted emails</span></span>

> [!IMPORTANT]
> <span data-ttu-id="300fc-214">メールをスキャンして変更するサード パーティ製のアプリケーションでは、OME ブランド化が正しく適用されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="300fc-214">Third-party applications that scan and modify mail can prevent OME branding from being applied correctly.</span></span>

<span data-ttu-id="300fc-215">既定のテンプレートを変更するか、新しいブランド 化テンプレートを作成したら、Exchange メール フロー ルールを作成して、特定の条件に基づいてカスタム ブランドを適用できます。</span><span class="sxs-lookup"><span data-stu-id="300fc-215">After you've either modified the default template or created new branding templates, you can create Exchange mail flow rules to apply your custom branding based on certain conditions.</span></span> <span data-ttu-id="300fc-216">このようなルールは、次のシナリオでカスタム ブランド化を適用します。</span><span class="sxs-lookup"><span data-stu-id="300fc-216">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="300fc-217">電子メールがエンド ユーザーによって手動で暗号化された場合は、以前は OutlookまたはOutlook on the webを使用Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="300fc-217">If the email was manually encrypted by the end user using Outlook or Outlook on the web, formerly Outlook Web App</span></span>

- <span data-ttu-id="300fc-218">メール フロー ルールまたはデータ損失防止ポリシー Exchangeによって電子メールが自動的に暗号化された場合</span><span class="sxs-lookup"><span data-stu-id="300fc-218">If the email was automatically encrypted by an Exchange mail flow rule or Data Loss Prevention policy</span></span>

<span data-ttu-id="300fc-219">暗号化を適用するメール フロー ルールExchange作成する方法については、「メール フロー ルールを定義してメール メッセージを暗号化する」を参照[Office 365。](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="300fc-219">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="300fc-220">Web ブラウザーで、グローバル管理者のアクセス許可が付与されている仕事または学校のアカウントを使用して、管理者に[サインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)Office 365。</span><span class="sxs-lookup"><span data-stu-id="300fc-220">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="300fc-221">[管理] **タイルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="300fc-221">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="300fc-222">Microsoft 365 管理センター で、**[管理センター]** \> **[Exchange]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="300fc-222">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="300fc-223">EAC で、[メールフロー ルール] に移動し、[新しい新しい] アイコン [ \>  ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **新しいルールの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="300fc-223">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="300fc-224">EAC の使用の詳細については、「Exchange[管理センター」を参照](/exchange/exchange-admin-center)Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="300fc-224">For more information about using the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="300fc-225">[ **名前]** に、営業部門のブランド化などのルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="300fc-225">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="300fc-226">[**このルールを適用する場合**]で、送信者が組織内にある条件と、使用可能な条件の一覧から必要なその他の条件を選択します。</span><span class="sxs-lookup"><span data-stu-id="300fc-226">In **Apply this rule if**, select the condition **The sender is located inside the organization** and other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="300fc-227">たとえば、特定のブランド テンプレートを次に適用できます。</span><span class="sxs-lookup"><span data-stu-id="300fc-227">For example, you might want to apply a particular branding template to:</span></span>

   - <span data-ttu-id="300fc-228">財務部門のメンバーから送信された暗号化されたメール</span><span class="sxs-lookup"><span data-stu-id="300fc-228">All encrypted emails sent from members of the finance department</span></span>
   - <span data-ttu-id="300fc-229">"外部" や "パートナー" などの特定のキーワードで送信される暗号化されたメール</span><span class="sxs-lookup"><span data-stu-id="300fc-229">Encrypted emails sent with a certain keyword such as "External" or "Partner"</span></span>
   - <span data-ttu-id="300fc-230">特定のドメインに送信される暗号化されたメール</span><span class="sxs-lookup"><span data-stu-id="300fc-230">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="300fc-231">[ **次の操作を行う**] で、[メッセージ セキュリティ **の変更]** [カスタム ブランドを \> **OME メッセージに適用する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="300fc-231">From **Do the following**, select **Modify the message security** \> **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="300fc-232">次に、ドロップダウンからブランド テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="300fc-232">Next, from the drop-down, select a branding template.</span></span>

8. <span data-ttu-id="300fc-233">(省略可能)暗号化とカスタム ブランド化を適用するメール フロー ルールを構成できます。</span><span class="sxs-lookup"><span data-stu-id="300fc-233">(Optional) You can configure the mail flow rule to apply encryption and custom branding.</span></span> <span data-ttu-id="300fc-234">[**次の操作を行う**] で、[メッセージ セキュリティ **の** 変更] を選択し、[セキュリティと **Office 365 Message Encryptionを適用する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="300fc-234">From **Do the following**, select **Modify the message security**, and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="300fc-235">一覧から RMS テンプレートを選択し、[保存]**を選択し\*\*\*\*、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="300fc-235">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
   <span data-ttu-id="300fc-236">テンプレートの一覧には、既定のテンプレートとオプション、および作成するカスタム テンプレートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="300fc-236">The list of templates includes default templates and options and any custom templates you create.</span></span> <span data-ttu-id="300fc-237">リストが空の場合は、新しい機能を使用してOffice 365 Message Encryption設定してください。</span><span class="sxs-lookup"><span data-stu-id="300fc-237">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities.</span></span> <span data-ttu-id="300fc-238">手順については、「新しい機能を[セットアップする」をOffice 365 Message Encryptionしてください](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="300fc-238">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="300fc-239">既定のテンプレートの詳細については、「Azure Information Protection 用テンプレートの構成と管理 [」を参照してください](/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="300fc-239">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="300fc-240">[転送しない] **オプションの詳細** については、「メールの [転送しないオプション」を参照してください](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="300fc-240">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="300fc-241">[暗号化のみ] オプション **の詳細については** 、「 [メールの暗号化のみオプション」を参照してください](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="300fc-241">For information about the **encrypt only** option, see [Encrypt Only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="300fc-242">別の **アクションを指定** する場合は、[アクションの追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="300fc-242">Choose **add action** if you want to specify another action.</span></span>

## <a name="background-color-reference"></a><span data-ttu-id="300fc-243">背景色の参照</span><span class="sxs-lookup"><span data-stu-id="300fc-243">Background color reference</span></span>

<span data-ttu-id="300fc-244">背景色に使用できる色名は制限されています。</span><span class="sxs-lookup"><span data-stu-id="300fc-244">The color names that you can use for the background color are limited.</span></span> <span data-ttu-id="300fc-245">色名の代わりに、16 進コード値 (#RRGGBB) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="300fc-245">Instead of a color name, you can use a hex code value (#RRGGBB).</span></span> <span data-ttu-id="300fc-246">色名に対応する 16 進コード値を使用するか、カスタムの 16 進コード値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="300fc-246">You can use a hex code value that corresponds to a color name, or you can use a custom hex code value.</span></span> <span data-ttu-id="300fc-247">16 進コードの値を二重引用符 (たとえば) で囲んでください `"#f0f8ff"` 。</span><span class="sxs-lookup"><span data-stu-id="300fc-247">Be sure to enclose the hex code value in quotation marks (for example, `"#f0f8ff"`).</span></span>

<span data-ttu-id="300fc-248">使用可能な背景色名と対応する 16 進コード値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="300fc-248">The available background color names and their corresponding hex code values are described in the following table.</span></span>

|<span data-ttu-id="300fc-249">**色の名前**</span><span class="sxs-lookup"><span data-stu-id="300fc-249">**Color name**</span></span>|<span data-ttu-id="300fc-250">**カラー コード**</span><span class="sxs-lookup"><span data-stu-id="300fc-250">**Color code**</span></span>|
|---|---|
|`aliceblue`|<span data-ttu-id="300fc-251">#f0f8ff</span><span class="sxs-lookup"><span data-stu-id="300fc-251">#f0f8ff</span></span>|
|`antiquewhite`|<span data-ttu-id="300fc-252">#faebd7</span><span class="sxs-lookup"><span data-stu-id="300fc-252">#faebd7</span></span>|
|`aqua`|<span data-ttu-id="300fc-253">#00ffff</span><span class="sxs-lookup"><span data-stu-id="300fc-253">#00ffff</span></span>|
|`aquamarine`|<span data-ttu-id="300fc-254">#7fffd4</span><span class="sxs-lookup"><span data-stu-id="300fc-254">#7fffd4</span></span>|
|`azure`|<span data-ttu-id="300fc-255">#f0ffff</span><span class="sxs-lookup"><span data-stu-id="300fc-255">#f0ffff</span></span>|
|`beige`|<span data-ttu-id="300fc-256">#f5f5dc</span><span class="sxs-lookup"><span data-stu-id="300fc-256">#f5f5dc</span></span>|
|`bisque`|<span data-ttu-id="300fc-257">#ffe4c4</span><span class="sxs-lookup"><span data-stu-id="300fc-257">#ffe4c4</span></span>|
|`black`|<span data-ttu-id="300fc-258">#000000</span><span class="sxs-lookup"><span data-stu-id="300fc-258">#000000</span></span>|
|`blanchedalmond`|<span data-ttu-id="300fc-259">#ffebcd</span><span class="sxs-lookup"><span data-stu-id="300fc-259">#ffebcd</span></span>|
|`blue`|<span data-ttu-id="300fc-260">#0000ff</span><span class="sxs-lookup"><span data-stu-id="300fc-260">#0000ff</span></span>|
|`blueviolet`|<span data-ttu-id="300fc-261">#8a2be2</span><span class="sxs-lookup"><span data-stu-id="300fc-261">#8a2be2</span></span>|
|`brown`|<span data-ttu-id="300fc-262">#a52a2a</span><span class="sxs-lookup"><span data-stu-id="300fc-262">#a52a2a</span></span>|
|`burlywood`|<span data-ttu-id="300fc-263">#deb887</span><span class="sxs-lookup"><span data-stu-id="300fc-263">#deb887</span></span>|
|`cadetblue`|<span data-ttu-id="300fc-264">#5f9ea0</span><span class="sxs-lookup"><span data-stu-id="300fc-264">#5f9ea0</span></span>|
|`chartreuse`|<span data-ttu-id="300fc-265">#7fff00</span><span class="sxs-lookup"><span data-stu-id="300fc-265">#7fff00</span></span>|
|`chocolate`|<span data-ttu-id="300fc-266">#d2691e</span><span class="sxs-lookup"><span data-stu-id="300fc-266">#d2691e</span></span>|
|`coral`|<span data-ttu-id="300fc-267">#ff7f50</span><span class="sxs-lookup"><span data-stu-id="300fc-267">#ff7f50</span></span>|
|`cornflowerblue`|<span data-ttu-id="300fc-268">#6495ed</span><span class="sxs-lookup"><span data-stu-id="300fc-268">#6495ed</span></span>|
|`cornsilk`|<span data-ttu-id="300fc-269">#fff8dc</span><span class="sxs-lookup"><span data-stu-id="300fc-269">#fff8dc</span></span>|
|`crimson`|<span data-ttu-id="300fc-270">#dc143c</span><span class="sxs-lookup"><span data-stu-id="300fc-270">#dc143c</span></span>|
|`cyan`|<span data-ttu-id="300fc-271">#00ffff</span><span class="sxs-lookup"><span data-stu-id="300fc-271">#00ffff</span></span>|
|`darkblue`|<span data-ttu-id="300fc-272">#00008b</span><span class="sxs-lookup"><span data-stu-id="300fc-272">#00008b</span></span>|
|`darkcyan`|<span data-ttu-id="300fc-273">#008b8b</span><span class="sxs-lookup"><span data-stu-id="300fc-273">#008b8b</span></span>|
|`darkgoldenrod`|<span data-ttu-id="300fc-274">#b8860b</span><span class="sxs-lookup"><span data-stu-id="300fc-274">#b8860b</span></span>|
|`darkgray`|<span data-ttu-id="300fc-275">#a9a9a9</span><span class="sxs-lookup"><span data-stu-id="300fc-275">#a9a9a9</span></span>|
|`darkgreen`|<span data-ttu-id="300fc-276">#006400</span><span class="sxs-lookup"><span data-stu-id="300fc-276">#006400</span></span>|
|`darkkhaki`|<span data-ttu-id="300fc-277">#bdb76b</span><span class="sxs-lookup"><span data-stu-id="300fc-277">#bdb76b</span></span>|
|`darkmagenta`|<span data-ttu-id="300fc-278">#8b008b</span><span class="sxs-lookup"><span data-stu-id="300fc-278">#8b008b</span></span>|
|`darkolivegreen`|<span data-ttu-id="300fc-279">#556b2f</span><span class="sxs-lookup"><span data-stu-id="300fc-279">#556b2f</span></span>|
|`darkorange`|<span data-ttu-id="300fc-280">#ff8c00</span><span class="sxs-lookup"><span data-stu-id="300fc-280">#ff8c00</span></span>|
|`darkorchid`|<span data-ttu-id="300fc-281">#9932cc</span><span class="sxs-lookup"><span data-stu-id="300fc-281">#9932cc</span></span>|
|`darkred`|<span data-ttu-id="300fc-282">#8b0000</span><span class="sxs-lookup"><span data-stu-id="300fc-282">#8b0000</span></span>|
|`darksalmon`|<span data-ttu-id="300fc-283">#e9967a</span><span class="sxs-lookup"><span data-stu-id="300fc-283">#e9967a</span></span>|
|`darkseagreen`|<span data-ttu-id="300fc-284">#8fbc8f</span><span class="sxs-lookup"><span data-stu-id="300fc-284">#8fbc8f</span></span>|
|`darkslateblue`|<span data-ttu-id="300fc-285">#483d8b</span><span class="sxs-lookup"><span data-stu-id="300fc-285">#483d8b</span></span>|
|`darkslategray`|<span data-ttu-id="300fc-286">#2f4f4f</span><span class="sxs-lookup"><span data-stu-id="300fc-286">#2f4f4f</span></span>|
|`darkturquoise`|<span data-ttu-id="300fc-287">#00ced1</span><span class="sxs-lookup"><span data-stu-id="300fc-287">#00ced1</span></span>|
|`darkviolet`|<span data-ttu-id="300fc-288">#9400d3</span><span class="sxs-lookup"><span data-stu-id="300fc-288">#9400d3</span></span>|
|`deeppink`|<span data-ttu-id="300fc-289">#ff1493</span><span class="sxs-lookup"><span data-stu-id="300fc-289">#ff1493</span></span>|
|`deepskyblue`|<span data-ttu-id="300fc-290">#00bfff</span><span class="sxs-lookup"><span data-stu-id="300fc-290">#00bfff</span></span>|
|`dimgray`|<span data-ttu-id="300fc-291">#696969</span><span class="sxs-lookup"><span data-stu-id="300fc-291">#696969</span></span>|
|`dodgerblue`|<span data-ttu-id="300fc-292">#1e90ff</span><span class="sxs-lookup"><span data-stu-id="300fc-292">#1e90ff</span></span>|
|`firebrick`|<span data-ttu-id="300fc-293">#b22222</span><span class="sxs-lookup"><span data-stu-id="300fc-293">#b22222</span></span>|
|`floralwhite`|<span data-ttu-id="300fc-294">#fffaf0</span><span class="sxs-lookup"><span data-stu-id="300fc-294">#fffaf0</span></span>|
|`forestgreen`|<span data-ttu-id="300fc-295">#228b22</span><span class="sxs-lookup"><span data-stu-id="300fc-295">#228b22</span></span>|
|`fuchsia`|<span data-ttu-id="300fc-296">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="300fc-296">#ff00ff</span></span>|
|`gainsboro`|<span data-ttu-id="300fc-297">#dcdcdc</span><span class="sxs-lookup"><span data-stu-id="300fc-297">#dcdcdc</span></span>|
|`ghostwhite`|<span data-ttu-id="300fc-298">#f8f8ff</span><span class="sxs-lookup"><span data-stu-id="300fc-298">#f8f8ff</span></span>|
|`gold`|<span data-ttu-id="300fc-299">#ffd700</span><span class="sxs-lookup"><span data-stu-id="300fc-299">#ffd700</span></span>|
|`goldenrod`|<span data-ttu-id="300fc-300">#daa520</span><span class="sxs-lookup"><span data-stu-id="300fc-300">#daa520</span></span>|
|`gray`|<span data-ttu-id="300fc-301">#808080</span><span class="sxs-lookup"><span data-stu-id="300fc-301">#808080</span></span>|
|`green`|<span data-ttu-id="300fc-302">#008000</span><span class="sxs-lookup"><span data-stu-id="300fc-302">#008000</span></span>|
|`greenyellow`|<span data-ttu-id="300fc-303">#adff2f</span><span class="sxs-lookup"><span data-stu-id="300fc-303">#adff2f</span></span>|
|`honeydew`|<span data-ttu-id="300fc-304">#f0fff0</span><span class="sxs-lookup"><span data-stu-id="300fc-304">#f0fff0</span></span>|
|`hotpink`|<span data-ttu-id="300fc-305">#ff69b4</span><span class="sxs-lookup"><span data-stu-id="300fc-305">#ff69b4</span></span>|
|`indianred`|<span data-ttu-id="300fc-306">#cd5c5c</span><span class="sxs-lookup"><span data-stu-id="300fc-306">#cd5c5c</span></span>|
|`indigo`|<span data-ttu-id="300fc-307">#4b0082</span><span class="sxs-lookup"><span data-stu-id="300fc-307">#4b0082</span></span>|
|`ivory`|<span data-ttu-id="300fc-308">#fffff0</span><span class="sxs-lookup"><span data-stu-id="300fc-308">#fffff0</span></span>|
|`khaki`|<span data-ttu-id="300fc-309">#f0e68c</span><span class="sxs-lookup"><span data-stu-id="300fc-309">#f0e68c</span></span>|
|`lavender`|<span data-ttu-id="300fc-310">#e6e6fa</span><span class="sxs-lookup"><span data-stu-id="300fc-310">#e6e6fa</span></span>|
|`lavenderblush`|<span data-ttu-id="300fc-311">#fff0f5</span><span class="sxs-lookup"><span data-stu-id="300fc-311">#fff0f5</span></span>|
|`lawngreen`|<span data-ttu-id="300fc-312">#7cfc00</span><span class="sxs-lookup"><span data-stu-id="300fc-312">#7cfc00</span></span>|
|`lemonchiffon`|<span data-ttu-id="300fc-313">#fffacd</span><span class="sxs-lookup"><span data-stu-id="300fc-313">#fffacd</span></span>|
|`lightblue`|<span data-ttu-id="300fc-314">#add8e6</span><span class="sxs-lookup"><span data-stu-id="300fc-314">#add8e6</span></span>|
|`lightcoral`|<span data-ttu-id="300fc-315">#f08080</span><span class="sxs-lookup"><span data-stu-id="300fc-315">#f08080</span></span>|
|`lightcyan`|<span data-ttu-id="300fc-316">#e0ffff</span><span class="sxs-lookup"><span data-stu-id="300fc-316">#e0ffff</span></span>|
|`lightgoldenrodyellow`|<span data-ttu-id="300fc-317">#fafad2</span><span class="sxs-lookup"><span data-stu-id="300fc-317">#fafad2</span></span>|
|`lightgray`|<span data-ttu-id="300fc-318">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="300fc-318">#d3d3d3</span></span>|
|`lightgrey`|<span data-ttu-id="300fc-319">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="300fc-319">#d3d3d3</span></span>|
|`lightgreen`|<span data-ttu-id="300fc-320">#90ee90</span><span class="sxs-lookup"><span data-stu-id="300fc-320">#90ee90</span></span>|
|`lightpink`|<span data-ttu-id="300fc-321">#ffb6c1</span><span class="sxs-lookup"><span data-stu-id="300fc-321">#ffb6c1</span></span>|
|`lightsalmon`|<span data-ttu-id="300fc-322">#ffa07a</span><span class="sxs-lookup"><span data-stu-id="300fc-322">#ffa07a</span></span>|
|`lightseagreen`|<span data-ttu-id="300fc-323">#20b2aa</span><span class="sxs-lookup"><span data-stu-id="300fc-323">#20b2aa</span></span>|
|`lightskyblue`|<span data-ttu-id="300fc-324">#87cefa</span><span class="sxs-lookup"><span data-stu-id="300fc-324">#87cefa</span></span>|
|`lightslategray`|<span data-ttu-id="300fc-325">#778899</span><span class="sxs-lookup"><span data-stu-id="300fc-325">#778899</span></span>|
|`lightsteelblue`|<span data-ttu-id="300fc-326">#b0c4de</span><span class="sxs-lookup"><span data-stu-id="300fc-326">#b0c4de</span></span>|
|`lightyellow`|<span data-ttu-id="300fc-327">#ffffe0</span><span class="sxs-lookup"><span data-stu-id="300fc-327">#ffffe0</span></span>|
|`lime`|<span data-ttu-id="300fc-328">#00ff00</span><span class="sxs-lookup"><span data-stu-id="300fc-328">#00ff00</span></span>|
|`limegreen`|<span data-ttu-id="300fc-329">#32cd32</span><span class="sxs-lookup"><span data-stu-id="300fc-329">#32cd32</span></span>|
|`linen`|<span data-ttu-id="300fc-330">#faf0e6</span><span class="sxs-lookup"><span data-stu-id="300fc-330">#faf0e6</span></span>|
|`magenta`|<span data-ttu-id="300fc-331">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="300fc-331">#ff00ff</span></span>|
|`maroon`|<span data-ttu-id="300fc-332">#800000</span><span class="sxs-lookup"><span data-stu-id="300fc-332">#800000</span></span>|
|`mediumaquamarine`|<span data-ttu-id="300fc-333">#66cdaa</span><span class="sxs-lookup"><span data-stu-id="300fc-333">#66cdaa</span></span>|
|`mediumblue`|<span data-ttu-id="300fc-334">#0000cd</span><span class="sxs-lookup"><span data-stu-id="300fc-334">#0000cd</span></span>|
|`mediumorchid`|<span data-ttu-id="300fc-335">#ba55d3</span><span class="sxs-lookup"><span data-stu-id="300fc-335">#ba55d3</span></span>|
|`mediumpurple`|<span data-ttu-id="300fc-336">#9370db</span><span class="sxs-lookup"><span data-stu-id="300fc-336">#9370db</span></span>|
|`mediumseagreen`|<span data-ttu-id="300fc-337">#3cb371</span><span class="sxs-lookup"><span data-stu-id="300fc-337">#3cb371</span></span>|
|`mediumslateblue`|<span data-ttu-id="300fc-338">#7b68ee</span><span class="sxs-lookup"><span data-stu-id="300fc-338">#7b68ee</span></span>|
|`mediumspringgreen`|<span data-ttu-id="300fc-339">#00fa9a</span><span class="sxs-lookup"><span data-stu-id="300fc-339">#00fa9a</span></span>|
|`mediumturquoise`|<span data-ttu-id="300fc-340">#48d1cc</span><span class="sxs-lookup"><span data-stu-id="300fc-340">#48d1cc</span></span>|
|`mediumvioletred`|<span data-ttu-id="300fc-341">#c71585</span><span class="sxs-lookup"><span data-stu-id="300fc-341">#c71585</span></span>|
|`midnightblue`|<span data-ttu-id="300fc-342">#191970</span><span class="sxs-lookup"><span data-stu-id="300fc-342">#191970</span></span>|
|`mintcream`|<span data-ttu-id="300fc-343">#f5fffa</span><span class="sxs-lookup"><span data-stu-id="300fc-343">#f5fffa</span></span>|
|`mistyrose`|<span data-ttu-id="300fc-344">#ffe4e1</span><span class="sxs-lookup"><span data-stu-id="300fc-344">#ffe4e1</span></span>|
|`moccasin`|<span data-ttu-id="300fc-345">#ffe4b5</span><span class="sxs-lookup"><span data-stu-id="300fc-345">#ffe4b5</span></span>|
|`navajowhite`|<span data-ttu-id="300fc-346">#ffdead</span><span class="sxs-lookup"><span data-stu-id="300fc-346">#ffdead</span></span>|
|`navy`|<span data-ttu-id="300fc-347">#000080</span><span class="sxs-lookup"><span data-stu-id="300fc-347">#000080</span></span>|
|`oldlace`|<span data-ttu-id="300fc-348">#fdf5e6</span><span class="sxs-lookup"><span data-stu-id="300fc-348">#fdf5e6</span></span>|
|`olive`|<span data-ttu-id="300fc-349">#808000</span><span class="sxs-lookup"><span data-stu-id="300fc-349">#808000</span></span>|
|`olivedrab`|<span data-ttu-id="300fc-350">#6b8e23</span><span class="sxs-lookup"><span data-stu-id="300fc-350">#6b8e23</span></span>|
|`orange`|<span data-ttu-id="300fc-351">#ffa500</span><span class="sxs-lookup"><span data-stu-id="300fc-351">#ffa500</span></span>|
|`orangered`|<span data-ttu-id="300fc-352">#ff4500</span><span class="sxs-lookup"><span data-stu-id="300fc-352">#ff4500</span></span>|
|`orchid`|<span data-ttu-id="300fc-353">#da70d6</span><span class="sxs-lookup"><span data-stu-id="300fc-353">#da70d6</span></span>|
|`palegoldenrod`|<span data-ttu-id="300fc-354">#eee8aa</span><span class="sxs-lookup"><span data-stu-id="300fc-354">#eee8aa</span></span>|
|`palegreen`|<span data-ttu-id="300fc-355">#98fb98</span><span class="sxs-lookup"><span data-stu-id="300fc-355">#98fb98</span></span>|
|`paleturquoise`|<span data-ttu-id="300fc-356">#afeeee</span><span class="sxs-lookup"><span data-stu-id="300fc-356">#afeeee</span></span>|
|`palevioletred`|<span data-ttu-id="300fc-357">#db7093</span><span class="sxs-lookup"><span data-stu-id="300fc-357">#db7093</span></span>|
|`papayawhip`|<span data-ttu-id="300fc-358">#ffefd5</span><span class="sxs-lookup"><span data-stu-id="300fc-358">#ffefd5</span></span>|
|`peachpuff`|<span data-ttu-id="300fc-359">#ffdab9</span><span class="sxs-lookup"><span data-stu-id="300fc-359">#ffdab9</span></span>|
|`peru`|<span data-ttu-id="300fc-360">#cd853f</span><span class="sxs-lookup"><span data-stu-id="300fc-360">#cd853f</span></span>|
|`pink`|<span data-ttu-id="300fc-361">#ffc0cb</span><span class="sxs-lookup"><span data-stu-id="300fc-361">#ffc0cb</span></span>|
|`plum`|<span data-ttu-id="300fc-362">#dda0dd</span><span class="sxs-lookup"><span data-stu-id="300fc-362">#dda0dd</span></span>|
|`powderblue`|<span data-ttu-id="300fc-363">#b0e0e6</span><span class="sxs-lookup"><span data-stu-id="300fc-363">#b0e0e6</span></span>|
|`purple`|<span data-ttu-id="300fc-364">#800080</span><span class="sxs-lookup"><span data-stu-id="300fc-364">#800080</span></span>|
|`red`|<span data-ttu-id="300fc-365">#ff0000</span><span class="sxs-lookup"><span data-stu-id="300fc-365">#ff0000</span></span>|
|`rosybrown`|<span data-ttu-id="300fc-366">#bc8f8f</span><span class="sxs-lookup"><span data-stu-id="300fc-366">#bc8f8f</span></span>|
|`royalblue`|<span data-ttu-id="300fc-367">#4169e1</span><span class="sxs-lookup"><span data-stu-id="300fc-367">#4169e1</span></span>|
|`saddlebrown`|<span data-ttu-id="300fc-368">#8b4513</span><span class="sxs-lookup"><span data-stu-id="300fc-368">#8b4513</span></span>|
|`salmon`|<span data-ttu-id="300fc-369">#fa8072</span><span class="sxs-lookup"><span data-stu-id="300fc-369">#fa8072</span></span>|
|`sandybrown`|<span data-ttu-id="300fc-370">#f4a460</span><span class="sxs-lookup"><span data-stu-id="300fc-370">#f4a460</span></span>|
|`seagreen`|<span data-ttu-id="300fc-371">#00ff00</span><span class="sxs-lookup"><span data-stu-id="300fc-371">#00ff00</span></span>|
|`seashell`|<span data-ttu-id="300fc-372">#fff5ee</span><span class="sxs-lookup"><span data-stu-id="300fc-372">#fff5ee</span></span>|
|`sienna`|<span data-ttu-id="300fc-373">#a0522d</span><span class="sxs-lookup"><span data-stu-id="300fc-373">#a0522d</span></span>|
|`silver`|<span data-ttu-id="300fc-374">#c0c0c0</span><span class="sxs-lookup"><span data-stu-id="300fc-374">#c0c0c0</span></span>|
|`skyblue`|<span data-ttu-id="300fc-375">#87ceeb</span><span class="sxs-lookup"><span data-stu-id="300fc-375">#87ceeb</span></span>|
|`slateblue`|<span data-ttu-id="300fc-376">#6a5acd</span><span class="sxs-lookup"><span data-stu-id="300fc-376">#6a5acd</span></span>|
|`slategray`|<span data-ttu-id="300fc-377">#708090</span><span class="sxs-lookup"><span data-stu-id="300fc-377">#708090</span></span>|
|`snow`|<span data-ttu-id="300fc-378">#fffafa</span><span class="sxs-lookup"><span data-stu-id="300fc-378">#fffafa</span></span>|
|`springgreen`|<span data-ttu-id="300fc-379">#00ff7f</span><span class="sxs-lookup"><span data-stu-id="300fc-379">#00ff7f</span></span>|
|`steelblue`|<span data-ttu-id="300fc-380">#4682b4</span><span class="sxs-lookup"><span data-stu-id="300fc-380">#4682b4</span></span>|
|`tan`|<span data-ttu-id="300fc-381">#d2b48c</span><span class="sxs-lookup"><span data-stu-id="300fc-381">#d2b48c</span></span>|
|`teal`|<span data-ttu-id="300fc-382">#008080</span><span class="sxs-lookup"><span data-stu-id="300fc-382">#008080</span></span>|
|`thistle`|<span data-ttu-id="300fc-383">#d8bfd8</span><span class="sxs-lookup"><span data-stu-id="300fc-383">#d8bfd8</span></span>|
|`tomato`|<span data-ttu-id="300fc-384">#ff6347</span><span class="sxs-lookup"><span data-stu-id="300fc-384">#ff6347</span></span>|
|`turquoise`|<span data-ttu-id="300fc-385">#40e0d0</span><span class="sxs-lookup"><span data-stu-id="300fc-385">#40e0d0</span></span>|
|`violet`|<span data-ttu-id="300fc-386">#ee82ee</span><span class="sxs-lookup"><span data-stu-id="300fc-386">#ee82ee</span></span>|
|`wheat`|<span data-ttu-id="300fc-387">#f5deb3</span><span class="sxs-lookup"><span data-stu-id="300fc-387">#f5deb3</span></span>|
|`white`|<span data-ttu-id="300fc-388">#ffffff</span><span class="sxs-lookup"><span data-stu-id="300fc-388">#ffffff</span></span>|
|`whitesmoke`|<span data-ttu-id="300fc-389">#f5f5f5</span><span class="sxs-lookup"><span data-stu-id="300fc-389">#f5f5f5</span></span>|
|`yellow`|<span data-ttu-id="300fc-390">#ffff00</span><span class="sxs-lookup"><span data-stu-id="300fc-390">#ffff00</span></span>|
|`yellowgreen`|<span data-ttu-id="300fc-391">#9acd32</span><span class="sxs-lookup"><span data-stu-id="300fc-391">#9acd32</span></span>|
