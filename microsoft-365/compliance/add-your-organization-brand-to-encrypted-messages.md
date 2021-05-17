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
ms.openlocfilehash: 2898e12ad00d11cd9eb2f3be5d817ef113607e79
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394715"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a><span data-ttu-id="f40bd-103">組織のブランドをビジネス メッセージ暗号化Microsoft 365メッセージに追加する</span><span class="sxs-lookup"><span data-stu-id="f40bd-103">Add your organization's brand to your Microsoft 365 for business Message Encryption encrypted messages</span></span>

<span data-ttu-id="f40bd-104">会社のブランド化を適用して、組織の電子メール メッセージと暗号化ポータルの外観をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f40bd-104">You can apply your company branding to customize the look of your organization's email messages and the encryption portal.</span></span> <span data-ttu-id="f40bd-105">作業を始める前に、グローバル管理者のアクセス許可を仕事または学校のアカウントに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f40bd-105">You'll need to apply global administrator permissions to your work or school account before you can get started.</span></span> <span data-ttu-id="f40bd-106">これらのアクセス許可を取得したら、Get-OMEConfigurationおよびSet-OMEConfiguration Windows PowerShellコマンドレットを使用して、暗号化された電子メール メッセージの次の部分をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="f40bd-106">Once you have these permissions, use the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets to customize these parts of encrypted email messages:</span></span>
  
- <span data-ttu-id="f40bd-107">入門テキスト</span><span class="sxs-lookup"><span data-stu-id="f40bd-107">Introductory text</span></span>

- <span data-ttu-id="f40bd-108">免責事項のテキスト</span><span class="sxs-lookup"><span data-stu-id="f40bd-108">Disclaimer text</span></span>

- <span data-ttu-id="f40bd-109">組織のプライバシーに関する声明の URL</span><span class="sxs-lookup"><span data-stu-id="f40bd-109">URL for Your organization's privacy statement</span></span>

- <span data-ttu-id="f40bd-110">OME ポータルのテキスト</span><span class="sxs-lookup"><span data-stu-id="f40bd-110">Text in the OME portal</span></span>

- <span data-ttu-id="f40bd-111">電子メール メッセージと OME ポータルに表示されるロゴ、またはロゴを使用するかどうか</span><span class="sxs-lookup"><span data-stu-id="f40bd-111">Logo that appears in the email message and OME portal, or whether to use a logo at all</span></span>

- <span data-ttu-id="f40bd-112">電子メール メッセージと OME ポータルの背景色</span><span class="sxs-lookup"><span data-stu-id="f40bd-112">Background color in the email message and OME portal</span></span>

<span data-ttu-id="f40bd-113">いつでも既定のルック アンド フィールに戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="f40bd-113">You can also revert back to the default look and feel at any time.</span></span>

<span data-ttu-id="f40bd-114">より詳細な制御が必要な場合は、Office 365 Advanced Message Encryptionを使用して、組織から送信される暗号化された電子メール用の複数のテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-114">If you'd like more control, use Office 365 Advanced Message Encryption to create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="f40bd-115">これらのテンプレートを使用して、エンド ユーザー エクスペリエンスの一部を制御します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-115">Use these templates to control parts of the end-user experience.</span></span> <span data-ttu-id="f40bd-116">たとえば、受信者が Google、Yahoo、Microsoft アカウントを使用して暗号化ポータルにサインインできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-116">For example, specify whether recipients can use Google, Yahoo, and Microsoft Accounts to sign in to the encryption portal.</span></span> <span data-ttu-id="f40bd-117">テンプレートを使用して、次のようないくつかの使用例を満たします。</span><span class="sxs-lookup"><span data-stu-id="f40bd-117">Use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="f40bd-118">財務、営業など、個々の部署。</span><span class="sxs-lookup"><span data-stu-id="f40bd-118">Individual departments, such as Finance, Sales, and so on.</span></span>

- <span data-ttu-id="f40bd-119">異なる製品</span><span class="sxs-lookup"><span data-stu-id="f40bd-119">Different products</span></span>

- <span data-ttu-id="f40bd-120">地理的な地域や国が異なる</span><span class="sxs-lookup"><span data-stu-id="f40bd-120">Different geographical regions or countries</span></span>

- <span data-ttu-id="f40bd-121">電子メールの取り消しを許可するかどうか</span><span class="sxs-lookup"><span data-stu-id="f40bd-121">Whether you want to allow emails to be revoked</span></span>

- <span data-ttu-id="f40bd-122">指定した日数を過ぎると、外部の受信者に送信されるメールの有効期限が切れるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-122">Whether you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="f40bd-123">テンプレートを作成したら、メール フロー ルールを使用して、暗号化されたExchange適用できます。</span><span class="sxs-lookup"><span data-stu-id="f40bd-123">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="f40bd-124">このテンプレートをOffice 365 Advanced Message Encryption、これらのテンプレートを使用してブランド化したメールを取り消します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-124">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>

## <a name="work-with-ome-branding-templates"></a><span data-ttu-id="f40bd-125">OME ブランド テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="f40bd-125">Work with OME branding templates</span></span>

<span data-ttu-id="f40bd-126">ブランド 化テンプレート内の複数の機能を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f40bd-126">You can modify several features within a branding template.</span></span> <span data-ttu-id="f40bd-127">既定のテンプレートは変更できますが、削除は行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f40bd-127">You can modify, but not remove, the default template.</span></span> <span data-ttu-id="f40bd-128">高度なメッセージ暗号化を使用している場合は、カスタム テンプレートを作成、変更、および削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="f40bd-128">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span> <span data-ttu-id="f40bd-129">このWindows PowerShellを使用して、一度に 1 つのブランド 化テンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-129">Use Windows PowerShell to work with one branding template at a time.</span></span>

- <span data-ttu-id="f40bd-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - 作成した既定のブランド テンプレートまたはカスタム ブランド テンプレートを変更します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - Modify the default branding template or a custom branding template that you created.</span></span>
- <span data-ttu-id="f40bd-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - 新しいブランド テンプレートを作成します。高度なメッセージ暗号化のみ。</span><span class="sxs-lookup"><span data-stu-id="f40bd-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - Create a new branding template, Advanced Message Encryption only.</span></span>
- <span data-ttu-id="f40bd-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - カスタム ブランド テンプレートの削除、高度なメッセージ暗号化のみ。</span><span class="sxs-lookup"><span data-stu-id="f40bd-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - Remove a custom branding template, Advanced Message Encryption only.</span></span> <span data-ttu-id="f40bd-133">既定のブランド 化テンプレートは削除できない。</span><span class="sxs-lookup"><span data-stu-id="f40bd-133">You can't delete the default branding template.</span></span>
  
## <a name="modify-an-ome-branding-template"></a><span data-ttu-id="f40bd-134">OME ブランド テンプレートの変更</span><span class="sxs-lookup"><span data-stu-id="f40bd-134">Modify an OME branding template</span></span>

<span data-ttu-id="f40bd-135">ブランドWindows PowerShell一度に 1 つのブランド テンプレートを変更するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-135">Use Windows PowerShell to modify one branding template at a time.</span></span> <span data-ttu-id="f40bd-136">高度なメッセージ暗号化を使用している場合は、カスタム テンプレートを作成、変更、および削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="f40bd-136">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span>

1. <span data-ttu-id="f40bd-137">組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="f40bd-137">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f40bd-138">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f40bd-138">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f40bd-139">[Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration)の説明に従って、Set-OMEConfigurationコマンドレットを使用するか、ガイダンスとして次の図と表を使用します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-139">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) or use the following graphic and table for guidance.</span></span>

![カスタマイズ可能な電子メール パーツ](../media/ome-template-breakout.png)

|<span data-ttu-id="f40bd-141">**カスタマイズする暗号化エクスペリエンスの特性**</span><span class="sxs-lookup"><span data-stu-id="f40bd-141">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="f40bd-142">**次のコマンドを使用する**</span><span class="sxs-lookup"><span data-stu-id="f40bd-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f40bd-143">背景色</span><span class="sxs-lookup"><span data-stu-id="f40bd-143">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> <span data-ttu-id="f40bd-144">**例:** </span><span class="sxs-lookup"><span data-stu-id="f40bd-144">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> <span data-ttu-id="f40bd-145">背景色の詳細については、この記事の後半の [「背景色](#background-color-reference) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f40bd-145">For more information about background colors, see the [Background colors](#background-color-reference) section later in this article.</span></span>|
|<span data-ttu-id="f40bd-146">ロゴ</span><span class="sxs-lookup"><span data-stu-id="f40bd-146">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> <span data-ttu-id="f40bd-147">**例:** </span><span class="sxs-lookup"><span data-stu-id="f40bd-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="f40bd-148">サポートされているファイル形式: .png、.jpg、.bmp、.tiff</span><span class="sxs-lookup"><span data-stu-id="f40bd-148">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="f40bd-149">ロゴ ファイルの最適なサイズ:40 KB 未満</span><span class="sxs-lookup"><span data-stu-id="f40bd-149">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="f40bd-150">ロゴ画像の最適なサイズ: 170x70 ピクセル。</span><span class="sxs-lookup"><span data-stu-id="f40bd-150">Optimal size of logo image: 170x70 pixels.</span></span> <span data-ttu-id="f40bd-151">画像がこれらのサイズを超えた場合、サービスはポータルに表示するロゴのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-151">If your image exceeds these dimensions, the service resizes your logo for display in the portal.</span></span> <span data-ttu-id="f40bd-152">サービスはグラフィック ファイル自体を変更しません。</span><span class="sxs-lookup"><span data-stu-id="f40bd-152">The service doesn't modify the graphic file itself.</span></span> <span data-ttu-id="f40bd-153">最適な結果を得る場合は、最適なサイズを使用します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-153">For best results, use the optimal size.</span></span>|
|<span data-ttu-id="f40bd-154">送信者の名前とメール アドレスの横にあるテキスト</span><span class="sxs-lookup"><span data-stu-id="f40bd-154">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="f40bd-155">**例:** </span><span class="sxs-lookup"><span data-stu-id="f40bd-155">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="f40bd-156">[メッセージの読み取り] ボタンに表示されるテキスト</span><span class="sxs-lookup"><span data-stu-id="f40bd-156">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="f40bd-157">**例:** </span><span class="sxs-lookup"><span data-stu-id="f40bd-157">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="f40bd-158">[メッセージの読み取り] ボタンの下に表示されるテキスト</span><span class="sxs-lookup"><span data-stu-id="f40bd-158">Text that appears below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="f40bd-159">**例:** </span><span class="sxs-lookup"><span data-stu-id="f40bd-159">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="f40bd-160">[プライバシーに関する声明] リンクの URL</span><span class="sxs-lookup"><span data-stu-id="f40bd-160">URL for the Privacy Statement link</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> <span data-ttu-id="f40bd-161">**例:** </span><span class="sxs-lookup"><span data-stu-id="f40bd-161">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|<span data-ttu-id="f40bd-162">暗号化メッセージを含む電子メールの免責文</span><span class="sxs-lookup"><span data-stu-id="f40bd-162">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="f40bd-163">**例:** </span><span class="sxs-lookup"><span data-stu-id="f40bd-163">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="f40bd-164">暗号化メールの表示ポータルの最上部に表示されるテキスト</span><span class="sxs-lookup"><span data-stu-id="f40bd-164">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="f40bd-165">**例:** </span><span class="sxs-lookup"><span data-stu-id="f40bd-165">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="f40bd-166">このカスタム テンプレートのワンタイム パス コードを使用して認証を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="f40bd-166">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="f40bd-167">**例:**</span><span class="sxs-lookup"><span data-stu-id="f40bd-167">**Examples:**</span></span> <br/><span data-ttu-id="f40bd-168">このカスタム テンプレートでワンタイム パスコードを有効にするには</span><span class="sxs-lookup"><span data-stu-id="f40bd-168">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="f40bd-169">このカスタム テンプレートのワンタイム パスコードを無効にするには</span><span class="sxs-lookup"><span data-stu-id="f40bd-169">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="f40bd-170">このカスタム テンプレートの Microsoft、Google、Yahoo ID を使用して認証を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="f40bd-170">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="f40bd-171">**例:**</span><span class="sxs-lookup"><span data-stu-id="f40bd-171">**Examples:**</span></span> <br/><span data-ttu-id="f40bd-172">このカスタム テンプレートのソーシャル ID を有効にするには</span><span class="sxs-lookup"><span data-stu-id="f40bd-172">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="f40bd-173">このカスタム テンプレートのソーシャル ID を無効にするには</span><span class="sxs-lookup"><span data-stu-id="f40bd-173">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a><span data-ttu-id="f40bd-174">OME ブランド テンプレートの作成 (高度なメッセージ暗号化)</span><span class="sxs-lookup"><span data-stu-id="f40bd-174">Create an OME branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="f40bd-175">このコマンドレットを[Office 365 Advanced Message Encryption、New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration)コマンドレットを使用して、組織のカスタム ブランド 化テンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f40bd-175">If you have Office 365 Advanced Message Encryption, you can create custom branding templates for your organization by using the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet.</span></span> <span data-ttu-id="f40bd-176">テンプレートを作成したら、「OME ブランド テンプレートの変更」の説明に従って、Set-OMEConfiguration コマンドレットを使用してテンプレート [を変更します](#modify-an-ome-branding-template)。</span><span class="sxs-lookup"><span data-stu-id="f40bd-176">Once you've created the template, you modify the template by using the Set-OMEConfiguration cmdlet as described in [Modify an OME branding template](#modify-an-ome-branding-template).</span></span> <span data-ttu-id="f40bd-177">複数のテンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f40bd-177">You can create multiple templates.</span></span>

<span data-ttu-id="f40bd-178">新しいカスタム ブランド テンプレートを作成するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-178">To create a new custom branding template:</span></span>

1. <span data-ttu-id="f40bd-179">組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="f40bd-179">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f40bd-180">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f40bd-180">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f40bd-181">[New-OMEConfiguration コマンドレットを使用して](/powershell/module/exchange/new-omeconfiguration)、新しいテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-181">Use the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   <span data-ttu-id="f40bd-182">例えば、</span><span class="sxs-lookup"><span data-stu-id="f40bd-182">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a><span data-ttu-id="f40bd-183">既定のブランド 化テンプレートを元の値に戻す</span><span class="sxs-lookup"><span data-stu-id="f40bd-183">Return the default branding template to its original values</span></span>

<span data-ttu-id="f40bd-184">ブランドのカスタマイズなど、既定のテンプレートからすべての変更を削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-184">To remove all modifications from the default template, including brand customizations, and so on, complete these steps:</span></span>
  
1. <span data-ttu-id="f40bd-185">組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="f40bd-185">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f40bd-186">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f40bd-186">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f40bd-187">**Set-OMEConfiguration** の説明に従って [、Set-OMEConfiguration コマンドレットを使用します](/powershell/module/exchange/Set-OMEConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="f40bd-187">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration).</span></span> <span data-ttu-id="f40bd-188">DisclaimerText、EmailText、PortalText の各値から組織のブランド化されたカスタマイズを削除するには、値を空の文字列に設定します `""` 。</span><span class="sxs-lookup"><span data-stu-id="f40bd-188">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string, `""`.</span></span> <span data-ttu-id="f40bd-189">Logo などのすべての画像値に対して、値をに設定します  `"$null"` 。</span><span class="sxs-lookup"><span data-stu-id="f40bd-189">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="f40bd-190">次の表では、暗号化カスタマイズ オプションの既定値について説明します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-190">The following table describes the encryption customization option defaults.</span></span>

   |<span data-ttu-id="f40bd-191">この暗号化の機能を既定のテキストと画像に戻すには</span><span class="sxs-lookup"><span data-stu-id="f40bd-191">To revert this feature of the encryption experience back to the default text and image</span></span>|<span data-ttu-id="f40bd-192">次のコマンドを使用する</span><span class="sxs-lookup"><span data-stu-id="f40bd-192">Use these commands</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="f40bd-193">暗号化された電子メール メッセージに付属する既定のテキスト。</span><span class="sxs-lookup"><span data-stu-id="f40bd-193">Default text that comes with encrypted email messages.</span></span>  <span data-ttu-id="f40bd-194">暗号化メッセージの表示手順の上に表示される既定のテキスト</span><span class="sxs-lookup"><span data-stu-id="f40bd-194">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> <span data-ttu-id="f40bd-195">**例:** </span><span class="sxs-lookup"><span data-stu-id="f40bd-195">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |<span data-ttu-id="f40bd-196">暗号化メッセージを含む電子メールの免責文</span><span class="sxs-lookup"><span data-stu-id="f40bd-196">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> <span data-ttu-id="f40bd-197">**例:** </span><span class="sxs-lookup"><span data-stu-id="f40bd-197">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |<span data-ttu-id="f40bd-198">暗号化メールの表示ポータルの最上部に表示されるテキスト</span><span class="sxs-lookup"><span data-stu-id="f40bd-198">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> <span data-ttu-id="f40bd-199">**既定に戻す例:**</span><span class="sxs-lookup"><span data-stu-id="f40bd-199">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |<span data-ttu-id="f40bd-200">ロゴ</span><span class="sxs-lookup"><span data-stu-id="f40bd-200">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> <span data-ttu-id="f40bd-201">**既定に戻す例:**</span><span class="sxs-lookup"><span data-stu-id="f40bd-201">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |<span data-ttu-id="f40bd-202">背景色</span><span class="sxs-lookup"><span data-stu-id="f40bd-202">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> <span data-ttu-id="f40bd-203">**既定に戻す例:**</span><span class="sxs-lookup"><span data-stu-id="f40bd-203">**Example reverting back to default:**</span></span> <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a><span data-ttu-id="f40bd-204">カスタム ブランド テンプレートを削除する (高度なメッセージ暗号化)</span><span class="sxs-lookup"><span data-stu-id="f40bd-204">Remove a custom branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="f40bd-205">削除または削除できるのは、作成したブランド 化テンプレートのみです。</span><span class="sxs-lookup"><span data-stu-id="f40bd-205">You can only remove or delete branding templates that you've made.</span></span> <span data-ttu-id="f40bd-206">既定のブランド 化テンプレートを削除できない。</span><span class="sxs-lookup"><span data-stu-id="f40bd-206">You can't remove the default branding template.</span></span>

<span data-ttu-id="f40bd-207">カスタム ブランド テンプレートを削除するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-207">To remove a custom branding template:</span></span>
  
1. <span data-ttu-id="f40bd-208">組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="f40bd-208">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f40bd-209">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f40bd-209">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f40bd-210">次のように **Remove-OMEConfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-210">Use the **Remove-OMEConfiguration** cmdlet as follows:</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   <span data-ttu-id="f40bd-211">例えば、</span><span class="sxs-lookup"><span data-stu-id="f40bd-211">For example,</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   <span data-ttu-id="f40bd-212">詳細については [、「Remove-OMEConfiguration」を参照してください](/powershell/module/exchange/remove-omeconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="f40bd-212">For more information, see [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration).</span></span>

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a><span data-ttu-id="f40bd-213">カスタム ブランドExchange暗号化されたメールに適用するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="f40bd-213">Create an Exchange mail flow rule that applies your custom branding to encrypted emails</span></span>

<span data-ttu-id="f40bd-214">既定のテンプレートを変更するか、新しいブランド 化テンプレートを作成したら、Exchange メール フロー ルールを作成して、特定の条件に基づいてカスタム ブランドを適用できます。</span><span class="sxs-lookup"><span data-stu-id="f40bd-214">After you've either modified the default template or created new branding templates, you can create Exchange mail flow rules to apply your custom branding based on certain conditions.</span></span> <span data-ttu-id="f40bd-215">このようなルールは、次のシナリオでカスタム ブランド化を適用します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-215">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="f40bd-216">電子メールが Web 上のユーザーまたはユーザーを使用してエンド Outlook手動Outlook暗号化された場合は、以前はOutlook Web App</span><span class="sxs-lookup"><span data-stu-id="f40bd-216">If the email was manually encrypted by the end user using Outlook or Outlook on the web, formerly Outlook Web App</span></span>

- <span data-ttu-id="f40bd-217">メール フロー ルールまたはデータ損失防止ポリシー Exchangeによって電子メールが自動的に暗号化された場合</span><span class="sxs-lookup"><span data-stu-id="f40bd-217">If the email was automatically encrypted by an Exchange mail flow rule or Data Loss Prevention policy</span></span>

<span data-ttu-id="f40bd-218">暗号化を適用するメール フロー ルールExchange作成する方法については、「メール フロー ルールを定義してメール メッセージを暗号化する」を参照[Office 365。](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="f40bd-218">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="f40bd-219">Web ブラウザーで、グローバル管理者のアクセス許可が付与されている仕事または学校のアカウントを使用して、管理者に[サインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)Office 365。</span><span class="sxs-lookup"><span data-stu-id="f40bd-219">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="f40bd-220">[管理] **タイルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-220">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="f40bd-221">Microsoft 365 管理センター で、**[管理センター]** \> **[Exchange]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-221">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="f40bd-222">EAC で、[メールフロー ルール] に移動し、[新しい新しい] アイコン [ \>  ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **新しいルールの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f40bd-222">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="f40bd-223">EAC の使用の詳細については、「Exchange[管理センター」を参照](/exchange/exchange-admin-center)Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="f40bd-223">For more information about using the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="f40bd-224">[ **名前]** に、営業部門のブランド化などのルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-224">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="f40bd-225">[**このルールを適用する場合**]で、送信者が組織内にある条件と、使用可能な条件の一覧から必要なその他の条件を選択します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-225">In **Apply this rule if**, select the condition **The sender is located inside the organization** and other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="f40bd-226">たとえば、特定のブランド テンプレートを次に適用できます。</span><span class="sxs-lookup"><span data-stu-id="f40bd-226">For example, you might want to apply a particular branding template to:</span></span>

   - <span data-ttu-id="f40bd-227">財務部門のメンバーから送信された暗号化されたメール</span><span class="sxs-lookup"><span data-stu-id="f40bd-227">All encrypted emails sent from members of the finance department</span></span>
   - <span data-ttu-id="f40bd-228">"外部" や "パートナー" などの特定のキーワードで送信される暗号化されたメール</span><span class="sxs-lookup"><span data-stu-id="f40bd-228">Encrypted emails sent with a certain keyword such as "External" or "Partner"</span></span>
   - <span data-ttu-id="f40bd-229">特定のドメインに送信される暗号化されたメール</span><span class="sxs-lookup"><span data-stu-id="f40bd-229">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="f40bd-230">[ **次の操作を行う**] で、[メッセージ セキュリティ **の変更]** [カスタム ブランドを \> **OME メッセージに適用する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f40bd-230">From **Do the following**, select **Modify the message security** \> **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="f40bd-231">次に、ドロップダウンからブランド テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-231">Next, from the drop-down, select a branding template.</span></span>

8. <span data-ttu-id="f40bd-232">(省略可能)暗号化とカスタム ブランド化を適用するメール フロー ルールを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f40bd-232">(Optional) You can configure the mail flow rule to apply encryption and custom branding.</span></span> <span data-ttu-id="f40bd-233">[**次の操作を行う**] で、[メッセージ セキュリティ **の** 変更] を選択し、[セキュリティと **Office 365 Message Encryptionを適用する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f40bd-233">From **Do the following**, select **Modify the message security**, and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="f40bd-234">一覧から RMS テンプレートを選択し、[保存]**を選択し\*\*\*\*、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f40bd-234">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
   <span data-ttu-id="f40bd-235">テンプレートの一覧には、既定のテンプレートとオプション、および作成するカスタム テンプレートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f40bd-235">The list of templates includes default templates and options and any custom templates you create.</span></span> <span data-ttu-id="f40bd-236">リストが空の場合は、新しい機能を使用してOffice 365 Message Encryption設定してください。</span><span class="sxs-lookup"><span data-stu-id="f40bd-236">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities.</span></span> <span data-ttu-id="f40bd-237">手順については、「新しい機能を[セットアップする」をOffice 365 Message Encryptionしてください](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="f40bd-237">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="f40bd-238">既定のテンプレートの詳細については、「Azure Information Protection 用テンプレートの構成と管理 [」を参照してください](/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="f40bd-238">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="f40bd-239">[転送しない] **オプションの詳細** については、「メールの [転送しないオプション」を参照してください](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="f40bd-239">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="f40bd-240">[暗号化のみ] オプション **の詳細については** 、「 [メールの暗号化のみオプション」を参照してください](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="f40bd-240">For information about the **encrypt only** option, see [Encrypt Only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="f40bd-241">別の **アクションを指定** する場合は、[アクションの追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-241">Choose **add action** if you want to specify another action.</span></span>

## <a name="background-color-reference"></a><span data-ttu-id="f40bd-242">背景色の参照</span><span class="sxs-lookup"><span data-stu-id="f40bd-242">Background color reference</span></span>

<span data-ttu-id="f40bd-243">背景色に使用できる色名は制限されています。</span><span class="sxs-lookup"><span data-stu-id="f40bd-243">The color names that you can use for the background color are limited.</span></span> <span data-ttu-id="f40bd-244">色名の代わりに、16 進コード値 (#RRGGBB) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f40bd-244">Instead of a color name, you can use a hex code value (#RRGGBB).</span></span> <span data-ttu-id="f40bd-245">色名に対応する 16 進コード値を使用するか、カスタムの 16 進コード値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f40bd-245">You can use a hex code value that corresponds to a color name, or you can use a custom hex code value.</span></span> <span data-ttu-id="f40bd-246">16 進コードの値を二重引用符 (たとえば) で囲んでください `"#f0f8ff"` 。</span><span class="sxs-lookup"><span data-stu-id="f40bd-246">Be sure to enclose the hex code value in quotation marks (for example, `"#f0f8ff"`).</span></span>

<span data-ttu-id="f40bd-247">使用可能な背景色名と対応する 16 進コード値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="f40bd-247">The available background color names and their corresponding hex code values are described in the following table.</span></span>

|<span data-ttu-id="f40bd-248">**色の名前**</span><span class="sxs-lookup"><span data-stu-id="f40bd-248">**Color name**</span></span>|<span data-ttu-id="f40bd-249">**カラー コード**</span><span class="sxs-lookup"><span data-stu-id="f40bd-249">**Color code**</span></span>|
|---|---|
|`aliceblue`|<span data-ttu-id="f40bd-250">#f0f8ff</span><span class="sxs-lookup"><span data-stu-id="f40bd-250">#f0f8ff</span></span>|
|`antiquewhite`|<span data-ttu-id="f40bd-251">#faebd7</span><span class="sxs-lookup"><span data-stu-id="f40bd-251">#faebd7</span></span>|
|`aqua`|<span data-ttu-id="f40bd-252">#00ffff</span><span class="sxs-lookup"><span data-stu-id="f40bd-252">#00ffff</span></span>|
|`aquamarine`|<span data-ttu-id="f40bd-253">#7fffd4</span><span class="sxs-lookup"><span data-stu-id="f40bd-253">#7fffd4</span></span>|
|`azure`|<span data-ttu-id="f40bd-254">#f0ffff</span><span class="sxs-lookup"><span data-stu-id="f40bd-254">#f0ffff</span></span>|
|`beige`|<span data-ttu-id="f40bd-255">#f5f5dc</span><span class="sxs-lookup"><span data-stu-id="f40bd-255">#f5f5dc</span></span>|
|`bisque`|<span data-ttu-id="f40bd-256">#ffe4c4</span><span class="sxs-lookup"><span data-stu-id="f40bd-256">#ffe4c4</span></span>|
|`black`|<span data-ttu-id="f40bd-257">#000000</span><span class="sxs-lookup"><span data-stu-id="f40bd-257">#000000</span></span>|
|`blanchedalmond`|<span data-ttu-id="f40bd-258">#ffebcd</span><span class="sxs-lookup"><span data-stu-id="f40bd-258">#ffebcd</span></span>|
|`blue`|<span data-ttu-id="f40bd-259">#0000ff</span><span class="sxs-lookup"><span data-stu-id="f40bd-259">#0000ff</span></span>|
|`blueviolet`|<span data-ttu-id="f40bd-260">#8a2be2</span><span class="sxs-lookup"><span data-stu-id="f40bd-260">#8a2be2</span></span>|
|`brown`|<span data-ttu-id="f40bd-261">#a52a2a</span><span class="sxs-lookup"><span data-stu-id="f40bd-261">#a52a2a</span></span>|
|`burlywood`|<span data-ttu-id="f40bd-262">#deb887</span><span class="sxs-lookup"><span data-stu-id="f40bd-262">#deb887</span></span>|
|`cadetblue`|<span data-ttu-id="f40bd-263">#5f9ea0</span><span class="sxs-lookup"><span data-stu-id="f40bd-263">#5f9ea0</span></span>|
|`chartreuse`|<span data-ttu-id="f40bd-264">#7fff00</span><span class="sxs-lookup"><span data-stu-id="f40bd-264">#7fff00</span></span>|
|`chocolate`|<span data-ttu-id="f40bd-265">#d2691e</span><span class="sxs-lookup"><span data-stu-id="f40bd-265">#d2691e</span></span>|
|`coral`|<span data-ttu-id="f40bd-266">#ff7f50</span><span class="sxs-lookup"><span data-stu-id="f40bd-266">#ff7f50</span></span>|
|`cornflowerblue`|<span data-ttu-id="f40bd-267">#6495ed</span><span class="sxs-lookup"><span data-stu-id="f40bd-267">#6495ed</span></span>|
|`cornsilk`|<span data-ttu-id="f40bd-268">#fff8dc</span><span class="sxs-lookup"><span data-stu-id="f40bd-268">#fff8dc</span></span>|
|`crimson`|<span data-ttu-id="f40bd-269">#dc143c</span><span class="sxs-lookup"><span data-stu-id="f40bd-269">#dc143c</span></span>|
|`cyan`|<span data-ttu-id="f40bd-270">#00ffff</span><span class="sxs-lookup"><span data-stu-id="f40bd-270">#00ffff</span></span>|
|`darkblue`|<span data-ttu-id="f40bd-271">#00008b</span><span class="sxs-lookup"><span data-stu-id="f40bd-271">#00008b</span></span>|
|`darkcyan`|<span data-ttu-id="f40bd-272">#008b8b</span><span class="sxs-lookup"><span data-stu-id="f40bd-272">#008b8b</span></span>|
|`darkgoldenrod`|<span data-ttu-id="f40bd-273">#b8860b</span><span class="sxs-lookup"><span data-stu-id="f40bd-273">#b8860b</span></span>|
|`darkgray`|<span data-ttu-id="f40bd-274">#a9a9a9</span><span class="sxs-lookup"><span data-stu-id="f40bd-274">#a9a9a9</span></span>|
|`darkgreen`|<span data-ttu-id="f40bd-275">#006400</span><span class="sxs-lookup"><span data-stu-id="f40bd-275">#006400</span></span>|
|`darkkhaki`|<span data-ttu-id="f40bd-276">#bdb76b</span><span class="sxs-lookup"><span data-stu-id="f40bd-276">#bdb76b</span></span>|
|`darkmagenta`|<span data-ttu-id="f40bd-277">#8b008b</span><span class="sxs-lookup"><span data-stu-id="f40bd-277">#8b008b</span></span>|
|`darkolivegreen`|<span data-ttu-id="f40bd-278">#556b2f</span><span class="sxs-lookup"><span data-stu-id="f40bd-278">#556b2f</span></span>|
|`darkorange`|<span data-ttu-id="f40bd-279">#ff8c00</span><span class="sxs-lookup"><span data-stu-id="f40bd-279">#ff8c00</span></span>|
|`darkorchid`|<span data-ttu-id="f40bd-280">#9932cc</span><span class="sxs-lookup"><span data-stu-id="f40bd-280">#9932cc</span></span>|
|`darkred`|<span data-ttu-id="f40bd-281">#8b0000</span><span class="sxs-lookup"><span data-stu-id="f40bd-281">#8b0000</span></span>|
|`darksalmon`|<span data-ttu-id="f40bd-282">#e9967a</span><span class="sxs-lookup"><span data-stu-id="f40bd-282">#e9967a</span></span>|
|`darkseagreen`|<span data-ttu-id="f40bd-283">#8fbc8f</span><span class="sxs-lookup"><span data-stu-id="f40bd-283">#8fbc8f</span></span>|
|`darkslateblue`|<span data-ttu-id="f40bd-284">#483d8b</span><span class="sxs-lookup"><span data-stu-id="f40bd-284">#483d8b</span></span>|
|`darkslategray`|<span data-ttu-id="f40bd-285">#2f4f4f</span><span class="sxs-lookup"><span data-stu-id="f40bd-285">#2f4f4f</span></span>|
|`darkturquoise`|<span data-ttu-id="f40bd-286">#00ced1</span><span class="sxs-lookup"><span data-stu-id="f40bd-286">#00ced1</span></span>|
|`darkviolet`|<span data-ttu-id="f40bd-287">#9400d3</span><span class="sxs-lookup"><span data-stu-id="f40bd-287">#9400d3</span></span>|
|`deeppink`|<span data-ttu-id="f40bd-288">#ff1493</span><span class="sxs-lookup"><span data-stu-id="f40bd-288">#ff1493</span></span>|
|`deepskyblue`|<span data-ttu-id="f40bd-289">#00bfff</span><span class="sxs-lookup"><span data-stu-id="f40bd-289">#00bfff</span></span>|
|`dimgray`|<span data-ttu-id="f40bd-290">#696969</span><span class="sxs-lookup"><span data-stu-id="f40bd-290">#696969</span></span>|
|`dodgerblue`|<span data-ttu-id="f40bd-291">#1e90ff</span><span class="sxs-lookup"><span data-stu-id="f40bd-291">#1e90ff</span></span>|
|`firebrick`|<span data-ttu-id="f40bd-292">#b22222</span><span class="sxs-lookup"><span data-stu-id="f40bd-292">#b22222</span></span>|
|`floralwhite`|<span data-ttu-id="f40bd-293">#fffaf0</span><span class="sxs-lookup"><span data-stu-id="f40bd-293">#fffaf0</span></span>|
|`forestgreen`|<span data-ttu-id="f40bd-294">#228b22</span><span class="sxs-lookup"><span data-stu-id="f40bd-294">#228b22</span></span>|
|`fuchsia`|<span data-ttu-id="f40bd-295">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="f40bd-295">#ff00ff</span></span>|
|`gainsboro`|<span data-ttu-id="f40bd-296">#dcdcdc</span><span class="sxs-lookup"><span data-stu-id="f40bd-296">#dcdcdc</span></span>|
|`ghostwhite`|<span data-ttu-id="f40bd-297">#f8f8ff</span><span class="sxs-lookup"><span data-stu-id="f40bd-297">#f8f8ff</span></span>|
|`gold`|<span data-ttu-id="f40bd-298">#ffd700</span><span class="sxs-lookup"><span data-stu-id="f40bd-298">#ffd700</span></span>|
|`goldenrod`|<span data-ttu-id="f40bd-299">#daa520</span><span class="sxs-lookup"><span data-stu-id="f40bd-299">#daa520</span></span>|
|`gray`|<span data-ttu-id="f40bd-300">#808080</span><span class="sxs-lookup"><span data-stu-id="f40bd-300">#808080</span></span>|
|`green`|<span data-ttu-id="f40bd-301">#008000</span><span class="sxs-lookup"><span data-stu-id="f40bd-301">#008000</span></span>|
|`greenyellow`|<span data-ttu-id="f40bd-302">#adff2f</span><span class="sxs-lookup"><span data-stu-id="f40bd-302">#adff2f</span></span>|
|`honeydew`|<span data-ttu-id="f40bd-303">#f0fff0</span><span class="sxs-lookup"><span data-stu-id="f40bd-303">#f0fff0</span></span>|
|`hotpink`|<span data-ttu-id="f40bd-304">#ff69b4</span><span class="sxs-lookup"><span data-stu-id="f40bd-304">#ff69b4</span></span>|
|`indianred`|<span data-ttu-id="f40bd-305">#cd5c5c</span><span class="sxs-lookup"><span data-stu-id="f40bd-305">#cd5c5c</span></span>|
|`indigo`|<span data-ttu-id="f40bd-306">#4b0082</span><span class="sxs-lookup"><span data-stu-id="f40bd-306">#4b0082</span></span>|
|`ivory`|<span data-ttu-id="f40bd-307">#fffff0</span><span class="sxs-lookup"><span data-stu-id="f40bd-307">#fffff0</span></span>|
|`khaki`|<span data-ttu-id="f40bd-308">#f0e68c</span><span class="sxs-lookup"><span data-stu-id="f40bd-308">#f0e68c</span></span>|
|`lavender`|<span data-ttu-id="f40bd-309">#e6e6fa</span><span class="sxs-lookup"><span data-stu-id="f40bd-309">#e6e6fa</span></span>|
|`lavenderblush`|<span data-ttu-id="f40bd-310">#fff0f5</span><span class="sxs-lookup"><span data-stu-id="f40bd-310">#fff0f5</span></span>|
|`lawngreen`|<span data-ttu-id="f40bd-311">#7cfc00</span><span class="sxs-lookup"><span data-stu-id="f40bd-311">#7cfc00</span></span>|
|`lemonchiffon`|<span data-ttu-id="f40bd-312">#fffacd</span><span class="sxs-lookup"><span data-stu-id="f40bd-312">#fffacd</span></span>|
|`lightblue`|<span data-ttu-id="f40bd-313">#add8e6</span><span class="sxs-lookup"><span data-stu-id="f40bd-313">#add8e6</span></span>|
|`lightcoral`|<span data-ttu-id="f40bd-314">#f08080</span><span class="sxs-lookup"><span data-stu-id="f40bd-314">#f08080</span></span>|
|`lightcyan`|<span data-ttu-id="f40bd-315">#e0ffff</span><span class="sxs-lookup"><span data-stu-id="f40bd-315">#e0ffff</span></span>|
|`lightgoldenrodyellow`|<span data-ttu-id="f40bd-316">#fafad2</span><span class="sxs-lookup"><span data-stu-id="f40bd-316">#fafad2</span></span>|
|`lightgray`|<span data-ttu-id="f40bd-317">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="f40bd-317">#d3d3d3</span></span>|
|`lightgrey`|<span data-ttu-id="f40bd-318">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="f40bd-318">#d3d3d3</span></span>|
|`lightgreen`|<span data-ttu-id="f40bd-319">#90ee90</span><span class="sxs-lookup"><span data-stu-id="f40bd-319">#90ee90</span></span>|
|`lightpink`|<span data-ttu-id="f40bd-320">#ffb6c1</span><span class="sxs-lookup"><span data-stu-id="f40bd-320">#ffb6c1</span></span>|
|`lightsalmon`|<span data-ttu-id="f40bd-321">#ffa07a</span><span class="sxs-lookup"><span data-stu-id="f40bd-321">#ffa07a</span></span>|
|`lightseagreen`|<span data-ttu-id="f40bd-322">#20b2aa</span><span class="sxs-lookup"><span data-stu-id="f40bd-322">#20b2aa</span></span>|
|`lightskyblue`|<span data-ttu-id="f40bd-323">#87cefa</span><span class="sxs-lookup"><span data-stu-id="f40bd-323">#87cefa</span></span>|
|`lightslategray`|<span data-ttu-id="f40bd-324">#778899</span><span class="sxs-lookup"><span data-stu-id="f40bd-324">#778899</span></span>|
|`lightsteelblue`|<span data-ttu-id="f40bd-325">#b0c4de</span><span class="sxs-lookup"><span data-stu-id="f40bd-325">#b0c4de</span></span>|
|`lightyellow`|<span data-ttu-id="f40bd-326">#ffffe0</span><span class="sxs-lookup"><span data-stu-id="f40bd-326">#ffffe0</span></span>|
|`lime`|<span data-ttu-id="f40bd-327">#00ff00</span><span class="sxs-lookup"><span data-stu-id="f40bd-327">#00ff00</span></span>|
|`limegreen`|<span data-ttu-id="f40bd-328">#32cd32</span><span class="sxs-lookup"><span data-stu-id="f40bd-328">#32cd32</span></span>|
|`linen`|<span data-ttu-id="f40bd-329">#faf0e6</span><span class="sxs-lookup"><span data-stu-id="f40bd-329">#faf0e6</span></span>|
|`magenta`|<span data-ttu-id="f40bd-330">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="f40bd-330">#ff00ff</span></span>|
|`maroon`|<span data-ttu-id="f40bd-331">#800000</span><span class="sxs-lookup"><span data-stu-id="f40bd-331">#800000</span></span>|
|`mediumaquamarine`|<span data-ttu-id="f40bd-332">#66cdaa</span><span class="sxs-lookup"><span data-stu-id="f40bd-332">#66cdaa</span></span>|
|`mediumblue`|<span data-ttu-id="f40bd-333">#0000cd</span><span class="sxs-lookup"><span data-stu-id="f40bd-333">#0000cd</span></span>|
|`mediumorchid`|<span data-ttu-id="f40bd-334">#ba55d3</span><span class="sxs-lookup"><span data-stu-id="f40bd-334">#ba55d3</span></span>|
|`mediumpurple`|<span data-ttu-id="f40bd-335">#9370db</span><span class="sxs-lookup"><span data-stu-id="f40bd-335">#9370db</span></span>|
|`mediumseagreen`|<span data-ttu-id="f40bd-336">#3cb371</span><span class="sxs-lookup"><span data-stu-id="f40bd-336">#3cb371</span></span>|
|`mediumslateblue`|<span data-ttu-id="f40bd-337">#7b68ee</span><span class="sxs-lookup"><span data-stu-id="f40bd-337">#7b68ee</span></span>|
|`mediumspringgreen`|<span data-ttu-id="f40bd-338">#00fa9a</span><span class="sxs-lookup"><span data-stu-id="f40bd-338">#00fa9a</span></span>|
|`mediumturquoise`|<span data-ttu-id="f40bd-339">#48d1cc</span><span class="sxs-lookup"><span data-stu-id="f40bd-339">#48d1cc</span></span>|
|`mediumvioletred`|<span data-ttu-id="f40bd-340">#c71585</span><span class="sxs-lookup"><span data-stu-id="f40bd-340">#c71585</span></span>|
|`midnightblue`|<span data-ttu-id="f40bd-341">#191970</span><span class="sxs-lookup"><span data-stu-id="f40bd-341">#191970</span></span>|
|`mintcream`|<span data-ttu-id="f40bd-342">#f5fffa</span><span class="sxs-lookup"><span data-stu-id="f40bd-342">#f5fffa</span></span>|
|`mistyrose`|<span data-ttu-id="f40bd-343">#ffe4e1</span><span class="sxs-lookup"><span data-stu-id="f40bd-343">#ffe4e1</span></span>|
|`moccasin`|<span data-ttu-id="f40bd-344">#ffe4b5</span><span class="sxs-lookup"><span data-stu-id="f40bd-344">#ffe4b5</span></span>|
|`navajowhite`|<span data-ttu-id="f40bd-345">#ffdead</span><span class="sxs-lookup"><span data-stu-id="f40bd-345">#ffdead</span></span>|
|`navy`|<span data-ttu-id="f40bd-346">#000080</span><span class="sxs-lookup"><span data-stu-id="f40bd-346">#000080</span></span>|
|`oldlace`|<span data-ttu-id="f40bd-347">#fdf5e6</span><span class="sxs-lookup"><span data-stu-id="f40bd-347">#fdf5e6</span></span>|
|`olive`|<span data-ttu-id="f40bd-348">#808000</span><span class="sxs-lookup"><span data-stu-id="f40bd-348">#808000</span></span>|
|`olivedrab`|<span data-ttu-id="f40bd-349">#6b8e23</span><span class="sxs-lookup"><span data-stu-id="f40bd-349">#6b8e23</span></span>|
|`orange`|<span data-ttu-id="f40bd-350">#ffa500</span><span class="sxs-lookup"><span data-stu-id="f40bd-350">#ffa500</span></span>|
|`orangered`|<span data-ttu-id="f40bd-351">#ff4500</span><span class="sxs-lookup"><span data-stu-id="f40bd-351">#ff4500</span></span>|
|`orchid`|<span data-ttu-id="f40bd-352">#da70d6</span><span class="sxs-lookup"><span data-stu-id="f40bd-352">#da70d6</span></span>|
|`palegoldenrod`|<span data-ttu-id="f40bd-353">#eee8aa</span><span class="sxs-lookup"><span data-stu-id="f40bd-353">#eee8aa</span></span>|
|`palegreen`|<span data-ttu-id="f40bd-354">#98fb98</span><span class="sxs-lookup"><span data-stu-id="f40bd-354">#98fb98</span></span>|
|`paleturquoise`|<span data-ttu-id="f40bd-355">#afeeee</span><span class="sxs-lookup"><span data-stu-id="f40bd-355">#afeeee</span></span>|
|`palevioletred`|<span data-ttu-id="f40bd-356">#db7093</span><span class="sxs-lookup"><span data-stu-id="f40bd-356">#db7093</span></span>|
|`papayawhip`|<span data-ttu-id="f40bd-357">#ffefd5</span><span class="sxs-lookup"><span data-stu-id="f40bd-357">#ffefd5</span></span>|
|`peachpuff`|<span data-ttu-id="f40bd-358">#ffdab9</span><span class="sxs-lookup"><span data-stu-id="f40bd-358">#ffdab9</span></span>|
|`peru`|<span data-ttu-id="f40bd-359">#cd853f</span><span class="sxs-lookup"><span data-stu-id="f40bd-359">#cd853f</span></span>|
|`pink`|<span data-ttu-id="f40bd-360">#ffc0cb</span><span class="sxs-lookup"><span data-stu-id="f40bd-360">#ffc0cb</span></span>|
|`plum`|<span data-ttu-id="f40bd-361">#dda0dd</span><span class="sxs-lookup"><span data-stu-id="f40bd-361">#dda0dd</span></span>|
|`powderblue`|<span data-ttu-id="f40bd-362">#b0e0e6</span><span class="sxs-lookup"><span data-stu-id="f40bd-362">#b0e0e6</span></span>|
|`purple`|<span data-ttu-id="f40bd-363">#800080</span><span class="sxs-lookup"><span data-stu-id="f40bd-363">#800080</span></span>|
|`red`|<span data-ttu-id="f40bd-364">#ff0000</span><span class="sxs-lookup"><span data-stu-id="f40bd-364">#ff0000</span></span>|
|`rosybrown`|<span data-ttu-id="f40bd-365">#bc8f8f</span><span class="sxs-lookup"><span data-stu-id="f40bd-365">#bc8f8f</span></span>|
|`royalblue`|<span data-ttu-id="f40bd-366">#4169e1</span><span class="sxs-lookup"><span data-stu-id="f40bd-366">#4169e1</span></span>|
|`saddlebrown`|<span data-ttu-id="f40bd-367">#8b4513</span><span class="sxs-lookup"><span data-stu-id="f40bd-367">#8b4513</span></span>|
|`salmon`|<span data-ttu-id="f40bd-368">#fa8072</span><span class="sxs-lookup"><span data-stu-id="f40bd-368">#fa8072</span></span>|
|`sandybrown`|<span data-ttu-id="f40bd-369">#f4a460</span><span class="sxs-lookup"><span data-stu-id="f40bd-369">#f4a460</span></span>|
|`seagreen`|<span data-ttu-id="f40bd-370">#00ff00</span><span class="sxs-lookup"><span data-stu-id="f40bd-370">#00ff00</span></span>|
|`seashell`|<span data-ttu-id="f40bd-371">#fff5ee</span><span class="sxs-lookup"><span data-stu-id="f40bd-371">#fff5ee</span></span>|
|`sienna`|<span data-ttu-id="f40bd-372">#a0522d</span><span class="sxs-lookup"><span data-stu-id="f40bd-372">#a0522d</span></span>|
|`silver`|<span data-ttu-id="f40bd-373">#c0c0c0</span><span class="sxs-lookup"><span data-stu-id="f40bd-373">#c0c0c0</span></span>|
|`skyblue`|<span data-ttu-id="f40bd-374">#87ceeb</span><span class="sxs-lookup"><span data-stu-id="f40bd-374">#87ceeb</span></span>|
|`slateblue`|<span data-ttu-id="f40bd-375">#6a5acd</span><span class="sxs-lookup"><span data-stu-id="f40bd-375">#6a5acd</span></span>|
|`slategray`|<span data-ttu-id="f40bd-376">#708090</span><span class="sxs-lookup"><span data-stu-id="f40bd-376">#708090</span></span>|
|`snow`|<span data-ttu-id="f40bd-377">#fffafa</span><span class="sxs-lookup"><span data-stu-id="f40bd-377">#fffafa</span></span>|
|`springgreen`|<span data-ttu-id="f40bd-378">#00ff7f</span><span class="sxs-lookup"><span data-stu-id="f40bd-378">#00ff7f</span></span>|
|`steelblue`|<span data-ttu-id="f40bd-379">#4682b4</span><span class="sxs-lookup"><span data-stu-id="f40bd-379">#4682b4</span></span>|
|`tan`|<span data-ttu-id="f40bd-380">#d2b48c</span><span class="sxs-lookup"><span data-stu-id="f40bd-380">#d2b48c</span></span>|
|`teal`|<span data-ttu-id="f40bd-381">#008080</span><span class="sxs-lookup"><span data-stu-id="f40bd-381">#008080</span></span>|
|`thistle`|<span data-ttu-id="f40bd-382">#d8bfd8</span><span class="sxs-lookup"><span data-stu-id="f40bd-382">#d8bfd8</span></span>|
|`tomato`|<span data-ttu-id="f40bd-383">#ff6347</span><span class="sxs-lookup"><span data-stu-id="f40bd-383">#ff6347</span></span>|
|`turquoise`|<span data-ttu-id="f40bd-384">#40e0d0</span><span class="sxs-lookup"><span data-stu-id="f40bd-384">#40e0d0</span></span>|
|`violet`|<span data-ttu-id="f40bd-385">#ee82ee</span><span class="sxs-lookup"><span data-stu-id="f40bd-385">#ee82ee</span></span>|
|`wheat`|<span data-ttu-id="f40bd-386">#f5deb3</span><span class="sxs-lookup"><span data-stu-id="f40bd-386">#f5deb3</span></span>|
|`white`|<span data-ttu-id="f40bd-387">#ffffff</span><span class="sxs-lookup"><span data-stu-id="f40bd-387">#ffffff</span></span>|
|`whitesmoke`|<span data-ttu-id="f40bd-388">#f5f5f5</span><span class="sxs-lookup"><span data-stu-id="f40bd-388">#f5f5f5</span></span>|
|`yellow`|<span data-ttu-id="f40bd-389">#ffff00</span><span class="sxs-lookup"><span data-stu-id="f40bd-389">#ffff00</span></span>|
|`yellowgreen`|<span data-ttu-id="f40bd-390">#9acd32</span><span class="sxs-lookup"><span data-stu-id="f40bd-390">#9acd32</span></span>|