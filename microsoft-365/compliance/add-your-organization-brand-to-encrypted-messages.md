---
title: 暗号化されたメッセージに組織のブランドを追加する
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
description: 365 Office管理者が暗号化ポータルのコンテンツを使用して暗号化された電子メール メッセージに組織の&を適用する方法について学習します。
ms.openlocfilehash: 77fd5e08afa1a4d8ae5f6386fa65b88b6ea2be4d
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663234"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a><span data-ttu-id="96450-103">組織のブランドを Microsoft 365 for Business Message Encryption で暗号化されたメッセージに追加する</span><span class="sxs-lookup"><span data-stu-id="96450-103">Add your organization's brand to your Microsoft 365 for business Message Encryption encrypted messages</span></span>

<span data-ttu-id="96450-104">会社のブランド化を適用して、組織の電子メール メッセージと暗号化ポータルの外観をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="96450-104">You can apply your company branding to customize the look of your organization's email messages and the encryption portal.</span></span> <span data-ttu-id="96450-105">作業を開始する前に、グローバル管理者のアクセス許可を仕事または学校のアカウントに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96450-105">You'll need to apply global administrator permissions to your work or school account before you can get started.</span></span> <span data-ttu-id="96450-106">これらのアクセス許可を取得したら、Get-OMEConfiguration コマンドレットと Set-OMEConfiguration Windows PowerShell コマンドレットを使用して、暗号化された電子メール メッセージの次の部分をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="96450-106">Once you have these permissions, use the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets to customize these parts of encrypted email messages:</span></span>
  
- <span data-ttu-id="96450-107">導入テキスト</span><span class="sxs-lookup"><span data-stu-id="96450-107">Introductory text</span></span>

- <span data-ttu-id="96450-108">免責事項テキスト</span><span class="sxs-lookup"><span data-stu-id="96450-108">Disclaimer text</span></span>

- <span data-ttu-id="96450-109">組織のプライバシーに関する声明の URL</span><span class="sxs-lookup"><span data-stu-id="96450-109">URL for Your organization's privacy statement</span></span>

- <span data-ttu-id="96450-110">OME ポータルのテキスト</span><span class="sxs-lookup"><span data-stu-id="96450-110">Text in the OME portal</span></span>

- <span data-ttu-id="96450-111">電子メール メッセージと OME ポータルに表示されるロゴ、またはロゴを使用するかどうか</span><span class="sxs-lookup"><span data-stu-id="96450-111">Logo that appears in the email message and OME portal, or whether to use a logo at all</span></span>

- <span data-ttu-id="96450-112">電子メール メッセージと OME ポータルの背景色</span><span class="sxs-lookup"><span data-stu-id="96450-112">Background color in the email message and OME portal</span></span>

<span data-ttu-id="96450-113">いつでも既定のルック アンド フィールに戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="96450-113">You can also revert back to the default look and feel at any time.</span></span>

<span data-ttu-id="96450-114">より詳細な制御が必要な場合は、Office 365 Advanced Message Encryption を使用して、組織から発信された暗号化された電子メール用の複数のテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="96450-114">If you'd like more control, use Office 365 Advanced Message Encryption to create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="96450-115">これらのテンプレートを使用して、エンド ユーザー エクスペリエンスの一部を制御します。</span><span class="sxs-lookup"><span data-stu-id="96450-115">Use these templates to control parts of the end-user experience.</span></span> <span data-ttu-id="96450-116">たとえば、受信者が Google、Yahoo、Microsoft アカウントを使用して暗号化ポータルにサインインできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="96450-116">For example, specify whether recipients can use Google, Yahoo, and Microsoft Accounts to sign in to the encryption portal.</span></span> <span data-ttu-id="96450-117">テンプレートを使用して、次のようないくつかの使用例を満たします。</span><span class="sxs-lookup"><span data-stu-id="96450-117">Use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="96450-118">財務、営業など、個々の部署。</span><span class="sxs-lookup"><span data-stu-id="96450-118">Individual departments, such as Finance, Sales, and so on.</span></span>

- <span data-ttu-id="96450-119">異なる製品</span><span class="sxs-lookup"><span data-stu-id="96450-119">Different products</span></span>

- <span data-ttu-id="96450-120">地理的に異なる地域または国</span><span class="sxs-lookup"><span data-stu-id="96450-120">Different geographical regions or countries</span></span>

- <span data-ttu-id="96450-121">メールの取り消しを許可するかどうかを指定します</span><span class="sxs-lookup"><span data-stu-id="96450-121">Whether you want to allow emails to be revoked</span></span>

- <span data-ttu-id="96450-122">外部の受信者に送信された電子メールを、指定した日数後に期限切れにするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="96450-122">Whether you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="96450-123">テンプレートを作成したら、Exchange メール フロー ルールを使用して、暗号化された電子メールにテンプレートを適用できます。</span><span class="sxs-lookup"><span data-stu-id="96450-123">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="96450-124">365 Advanced Message Encryption Office使用している場合は、これらのテンプレートを使用して、ブランド化したメールを取り消す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="96450-124">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>

## <a name="work-with-ome-branding-templates"></a><span data-ttu-id="96450-125">OME ブランド 化テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="96450-125">Work with OME branding templates</span></span>

<span data-ttu-id="96450-126">ブランド化テンプレート内のいくつかの機能を変更できます。</span><span class="sxs-lookup"><span data-stu-id="96450-126">You can modify several features within a branding template.</span></span> <span data-ttu-id="96450-127">既定のテンプレートは変更できますが、削除はできます。</span><span class="sxs-lookup"><span data-stu-id="96450-127">You can modify, but not remove, the default template.</span></span> <span data-ttu-id="96450-128">Advanced Message Encryption を使用している場合は、カスタム テンプレートを作成、変更、削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="96450-128">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span> <span data-ttu-id="96450-129">一Windows PowerShellを使用して 1 つのブランドテンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="96450-129">Use Windows PowerShell to work with one branding template at a time.</span></span>

- <span data-ttu-id="96450-130">[Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) - 作成した既定のブランドテンプレートまたはカスタム ブランド テンプレートを変更します。</span><span class="sxs-lookup"><span data-stu-id="96450-130">[Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) - Modify the default branding template or a custom branding template that you created.</span></span>
- <span data-ttu-id="96450-131">[New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) - 新しいブランドテンプレートを作成します。Advanced Message Encryption のみ。</span><span class="sxs-lookup"><span data-stu-id="96450-131">[New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) - Create a new branding template, Advanced Message Encryption only.</span></span>
- <span data-ttu-id="96450-132">[Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) - カスタム ブランド テンプレートを削除します。Advanced Message Encryption のみ。</span><span class="sxs-lookup"><span data-stu-id="96450-132">[Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) - Remove a custom branding template, Advanced Message Encryption only.</span></span> <span data-ttu-id="96450-133">既定のブランド化テンプレートは削除できない。</span><span class="sxs-lookup"><span data-stu-id="96450-133">You can't delete the default branding template.</span></span>
  
## <a name="modify-an-ome-branding-template"></a><span data-ttu-id="96450-134">OME ブランドテンプレートを変更する</span><span class="sxs-lookup"><span data-stu-id="96450-134">Modify an OME branding template</span></span>

<span data-ttu-id="96450-135">一Windows PowerShell 1 つのブランド テンプレートを変更するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="96450-135">Use Windows PowerShell to modify one branding template at a time.</span></span> <span data-ttu-id="96450-136">Advanced Message Encryption を使用している場合は、カスタム テンプレートを作成、変更、削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="96450-136">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span>

1. <span data-ttu-id="96450-137">組織のグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShellセッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="96450-137">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="96450-138">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96450-138">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="96450-139">[Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) Set-OMEConfiguration説明に従って次のコマンドレットを使用するか、ガイダンスとして次の図と表を使用します。</span><span class="sxs-lookup"><span data-stu-id="96450-139">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) or use the following graphic and table for guidance.</span></span>

![カスタマイズ可能な電子メール パーツ](../media/ome-template-breakout.png)

|<span data-ttu-id="96450-141">**カスタマイズする暗号化エクスペリエンスの特性**</span><span class="sxs-lookup"><span data-stu-id="96450-141">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="96450-142">**使用するコマンド**</span><span class="sxs-lookup"><span data-stu-id="96450-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="96450-143">背景色</span><span class="sxs-lookup"><span data-stu-id="96450-143">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> <span data-ttu-id="96450-144">**例:** </span><span class="sxs-lookup"><span data-stu-id="96450-144">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> <span data-ttu-id="96450-145">背景の色について詳しくは、この記事で後の「 [背景の](#background-color-reference) 色」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="96450-145">For more information about background colors, see the [Background colors](#background-color-reference) section later in this article.</span></span>|
|<span data-ttu-id="96450-146">ロゴ</span><span class="sxs-lookup"><span data-stu-id="96450-146">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> <span data-ttu-id="96450-147">**例:** </span><span class="sxs-lookup"><span data-stu-id="96450-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="96450-148">サポートされているファイル形式: .png、.jpg、.bmp、.tiff</span><span class="sxs-lookup"><span data-stu-id="96450-148">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="96450-149">ロゴ ファイルの最適なサイズ:40 KB 未満</span><span class="sxs-lookup"><span data-stu-id="96450-149">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="96450-150">ロゴ画像の最適なサイズ: 170x70 ピクセル。</span><span class="sxs-lookup"><span data-stu-id="96450-150">Optimal size of logo image: 170x70 pixels.</span></span> <span data-ttu-id="96450-151">画像がこれらのサイズを超える場合、サービスはポータルに表示するロゴのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="96450-151">If your image exceeds these dimensions, the service resizes your logo for display in the portal.</span></span> <span data-ttu-id="96450-152">サービスは、グラフィック ファイル自体を変更しません。</span><span class="sxs-lookup"><span data-stu-id="96450-152">The service doesn't modify the graphic file itself.</span></span> <span data-ttu-id="96450-153">最適な結果を得る場合は、最適なサイズを使用してください。</span><span class="sxs-lookup"><span data-stu-id="96450-153">For best results, use the optimal size.</span></span>|
|<span data-ttu-id="96450-154">送信者の名前とメール アドレスの横のテキスト</span><span class="sxs-lookup"><span data-stu-id="96450-154">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="96450-155">**例:** </span><span class="sxs-lookup"><span data-stu-id="96450-155">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="96450-156">[メッセージの読み取り] ボタンに表示されるテキスト</span><span class="sxs-lookup"><span data-stu-id="96450-156">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="96450-157">**例:** </span><span class="sxs-lookup"><span data-stu-id="96450-157">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="96450-158">[メッセージの読み取り] ボタンの下に表示されるテキスト</span><span class="sxs-lookup"><span data-stu-id="96450-158">Text that appears below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="96450-159">**例:** </span><span class="sxs-lookup"><span data-stu-id="96450-159">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="96450-160">[プライバシーに関する声明] リンクの URL</span><span class="sxs-lookup"><span data-stu-id="96450-160">URL for the Privacy Statement link</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> <span data-ttu-id="96450-161">**例:** </span><span class="sxs-lookup"><span data-stu-id="96450-161">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|<span data-ttu-id="96450-162">暗号化メッセージを含む電子メールの免責文</span><span class="sxs-lookup"><span data-stu-id="96450-162">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="96450-163">**例:** </span><span class="sxs-lookup"><span data-stu-id="96450-163">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="96450-164">暗号化メールの表示ポータルの最上部に表示されるテキスト</span><span class="sxs-lookup"><span data-stu-id="96450-164">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="96450-165">**例:** </span><span class="sxs-lookup"><span data-stu-id="96450-165">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="96450-166">このカスタム テンプレートのワンタイム パス コードを使用して認証を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="96450-166">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="96450-167">**例:**</span><span class="sxs-lookup"><span data-stu-id="96450-167">**Examples:**</span></span> <br/><span data-ttu-id="96450-168">このカスタム テンプレートのワンタイム パスコードを有効にするには</span><span class="sxs-lookup"><span data-stu-id="96450-168">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="96450-169">このカスタム テンプレートのワンタイム パスコードを無効にするには</span><span class="sxs-lookup"><span data-stu-id="96450-169">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="96450-170">このカスタム テンプレートの Microsoft、Google、または Yahoo ID を使用した認証を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="96450-170">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="96450-171">**例:**</span><span class="sxs-lookup"><span data-stu-id="96450-171">**Examples:**</span></span> <br/><span data-ttu-id="96450-172">このカスタム テンプレートのソーシャル ID を有効にするには</span><span class="sxs-lookup"><span data-stu-id="96450-172">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="96450-173">このカスタム テンプレートのソーシャル ID を無効にするには</span><span class="sxs-lookup"><span data-stu-id="96450-173">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a><span data-ttu-id="96450-174">OME ブランド化テンプレートを作成する (Advanced Message Encryption)</span><span class="sxs-lookup"><span data-stu-id="96450-174">Create an OME branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="96450-175">365 Advanced Message Encryption Officeしている場合は [、New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) コマンドレットを使用して、組織のカスタム ブランド テンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="96450-175">If you have Office 365 Advanced Message Encryption, you can create custom branding templates for your organization by using the [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) cmdlet.</span></span> <span data-ttu-id="96450-176">テンプレートを作成したら、「OME ブランド化テンプレートの変更」の説明に従って Set-OMEConfiguration コマンドレットを使用してテンプレート [を変更します](#modify-an-ome-branding-template)。</span><span class="sxs-lookup"><span data-stu-id="96450-176">Once you've created the template, you modify the template by using the Set-OMEConfiguration cmdlet as described in [Modify an OME branding template](#modify-an-ome-branding-template).</span></span> <span data-ttu-id="96450-177">複数のテンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="96450-177">You can create multiple templates.</span></span>

<span data-ttu-id="96450-178">新しいカスタム ブランドテンプレートを作成するには:</span><span class="sxs-lookup"><span data-stu-id="96450-178">To create a new custom branding template:</span></span>

1. <span data-ttu-id="96450-179">組織のグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShellセッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="96450-179">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="96450-180">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96450-180">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="96450-181">新しい [テンプレートを作成するには、New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="96450-181">Use the [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   <span data-ttu-id="96450-182">例えば、</span><span class="sxs-lookup"><span data-stu-id="96450-182">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a><span data-ttu-id="96450-183">既定のブランドテンプレートを元の値に戻す</span><span class="sxs-lookup"><span data-stu-id="96450-183">Return the default branding template to its original values</span></span>

<span data-ttu-id="96450-184">ブランドのカスタマイズなど、既定のテンプレートからすべての変更を削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="96450-184">To remove all modifications from the default template, including brand customizations, and so on, complete these steps:</span></span>
  
1. <span data-ttu-id="96450-185">組織のグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShellセッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="96450-185">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="96450-186">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96450-186">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="96450-187">**Set-OMEConfiguration コマンドレット** の説明に従 [って、Set-OMEConfiguration コマンドレットを使用します](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="96450-187">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration).</span></span> <span data-ttu-id="96450-188">DisclaimerText、EmailText、および PortalText の値から組織のブランド化されたカスタマイズを削除するには、値を空の文字列に設定します `""` 。</span><span class="sxs-lookup"><span data-stu-id="96450-188">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string, `""`.</span></span> <span data-ttu-id="96450-189">ロゴなどのすべての画像の値に対して、値を次のように設定します  `"$null"` 。</span><span class="sxs-lookup"><span data-stu-id="96450-189">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="96450-190">次の表では、暗号化カスタマイズ オプションの既定値について説明します。</span><span class="sxs-lookup"><span data-stu-id="96450-190">The following table describes the encryption customization option defaults.</span></span>

   <span data-ttu-id="96450-191">**この暗号化の機能を既定のテキストと画像に戻すには**</span><span class="sxs-lookup"><span data-stu-id="96450-191">**To revert this feature of the encryption experience back to the default text and image**</span></span>|<span data-ttu-id="96450-192">**使用するコマンド**</span><span class="sxs-lookup"><span data-stu-id="96450-192">**Use these commands**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="96450-193">暗号化された電子メール メッセージに付属する既定のテキスト</span><span class="sxs-lookup"><span data-stu-id="96450-193">Default text that comes with encrypted email messages</span></span>  <br/> <span data-ttu-id="96450-194">暗号化メッセージの表示手順の上に表示される既定のテキスト</span><span class="sxs-lookup"><span data-stu-id="96450-194">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> <span data-ttu-id="96450-195">**例:** </span><span class="sxs-lookup"><span data-stu-id="96450-195">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |<span data-ttu-id="96450-196">暗号化メッセージを含む電子メールの免責文</span><span class="sxs-lookup"><span data-stu-id="96450-196">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> <span data-ttu-id="96450-197">**例:** </span><span class="sxs-lookup"><span data-stu-id="96450-197">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |<span data-ttu-id="96450-198">暗号化メールの表示ポータルの最上部に表示されるテキスト</span><span class="sxs-lookup"><span data-stu-id="96450-198">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> <span data-ttu-id="96450-199">**既定値に戻す例:**</span><span class="sxs-lookup"><span data-stu-id="96450-199">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |<span data-ttu-id="96450-200">ロゴ</span><span class="sxs-lookup"><span data-stu-id="96450-200">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> <span data-ttu-id="96450-201">**既定値に戻す例:**</span><span class="sxs-lookup"><span data-stu-id="96450-201">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |<span data-ttu-id="96450-202">背景色</span><span class="sxs-lookup"><span data-stu-id="96450-202">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> <span data-ttu-id="96450-203">**既定値に戻す例:**</span><span class="sxs-lookup"><span data-stu-id="96450-203">**Example reverting back to default:**</span></span> <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a><span data-ttu-id="96450-204">カスタム ブランド テンプレートを削除する (Advanced Message Encryption)</span><span class="sxs-lookup"><span data-stu-id="96450-204">Remove a custom branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="96450-205">削除または削除できるのは、作成したブランド化テンプレートのみです。</span><span class="sxs-lookup"><span data-stu-id="96450-205">You can only remove or delete branding templates that you've made.</span></span> <span data-ttu-id="96450-206">既定のブランド化テンプレートは削除できない。</span><span class="sxs-lookup"><span data-stu-id="96450-206">You can't remove the default branding template.</span></span>

<span data-ttu-id="96450-207">カスタム ブランド テンプレートを削除するには:</span><span class="sxs-lookup"><span data-stu-id="96450-207">To remove a custom branding template:</span></span>
  
1. <span data-ttu-id="96450-208">組織のグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShellセッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="96450-208">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="96450-209">手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96450-209">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="96450-210">**Remove-OMEConfiguration コマンドレットは次** のように使用します。</span><span class="sxs-lookup"><span data-stu-id="96450-210">Use the **Remove-OMEConfiguration** cmdlet as follows:</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   <span data-ttu-id="96450-211">例えば、</span><span class="sxs-lookup"><span data-stu-id="96450-211">For example,</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   <span data-ttu-id="96450-212">詳細については [、「Remove-OMEConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="96450-212">For more information, see [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration).</span></span>

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a><span data-ttu-id="96450-213">暗号化されたメールにカスタム ブランドを適用する Exchange メール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="96450-213">Create an Exchange mail flow rule that applies your custom branding to encrypted emails</span></span>

<span data-ttu-id="96450-214">既定のテンプレートを変更するか、新しいブランド化テンプレートを作成したら、特定の条件に基づいてカスタム ブランド化を適用する Exchange メール フロー ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="96450-214">After you've either modified the default template or created new branding templates, you can create Exchange mail flow rules to apply your custom branding based on certain conditions.</span></span> <span data-ttu-id="96450-215">このようなルールは、次のシナリオでカスタム ブランド化を適用します。</span><span class="sxs-lookup"><span data-stu-id="96450-215">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="96450-216">電子メールが Outlook または Outlook on the web を使用してエンド ユーザーによって手動で暗号化された場合、以前はOutlook Web App</span><span class="sxs-lookup"><span data-stu-id="96450-216">If the email was manually encrypted by the end user using Outlook or Outlook on the web, formerly Outlook Web App</span></span>

- <span data-ttu-id="96450-217">Exchange メール フロー ルールまたはデータ損失防止ポリシーによって電子メールが自動的に暗号化された場合</span><span class="sxs-lookup"><span data-stu-id="96450-217">If the email was automatically encrypted by an Exchange mail flow rule or Data Loss Prevention policy</span></span>

<span data-ttu-id="96450-218">暗号化を適用する Exchange メール フロー ルールを作成する方法については [、「365](define-mail-flow-rules-to-encrypt-email.md)で電子メール メッセージを暗号化するメール フロー ルールを定義する」をOfficeしてください。</span><span class="sxs-lookup"><span data-stu-id="96450-218">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="96450-219">Web ブラウザーで、グローバル管理者のアクセス許可が付与されている学校または学校のアカウントを使用して、Office [365 にサインインします](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="96450-219">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="96450-220">[管理者] **タイルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="96450-220">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="96450-221">Microsoft 365 管理センターで、Exchange 管理センター **を選択** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="96450-221">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="96450-222">EAC で、[メール フロー ルール] に **移動** し、[新しい] アイコン [ \>  ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **新しいルールの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="96450-222">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="96450-223">EAC の使用の詳細については、Exchange Online の [Exchange 管理センターを参照してください](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="96450-223">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="96450-224">[ **名前]** に、営業部門のブランド化などのルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="96450-224">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="96450-225">[**次の場合に** このルールを適用する] で、送信者が組織内に存在する条件と、使用可能な条件の一覧から必要なその他の条件を選択します。</span><span class="sxs-lookup"><span data-stu-id="96450-225">In **Apply this rule if**, select the condition **The sender is located inside the organization** and other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="96450-226">たとえば、次の場合に特定のブランド化テンプレートを適用できます。</span><span class="sxs-lookup"><span data-stu-id="96450-226">For example, you might want to apply a particular branding template to:</span></span>

   - <span data-ttu-id="96450-227">財務部門のメンバーから送信された暗号化された電子メールすべて</span><span class="sxs-lookup"><span data-stu-id="96450-227">All encrypted emails sent from members of the finance department</span></span>
   - <span data-ttu-id="96450-228">"外部" や "パートナー" などの特定のキーワードで送信された暗号化された電子メール</span><span class="sxs-lookup"><span data-stu-id="96450-228">Encrypted emails sent with a certain keyword such as "External" or "Partner"</span></span>
   - <span data-ttu-id="96450-229">特定のドメインに送信される暗号化された電子メール</span><span class="sxs-lookup"><span data-stu-id="96450-229">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="96450-230">From **Do the following,** select **Modify the message security** Apply \> **custom branding to OME messages**.</span><span class="sxs-lookup"><span data-stu-id="96450-230">From **Do the following**, select **Modify the message security** \> **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="96450-231">次に、ドロップダウンからブランド テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="96450-231">Next, from the drop-down, select a branding template.</span></span>

8. <span data-ttu-id="96450-232">(省略可能)暗号化とカスタム ブランド化を適用するメール フロー ルールを構成できます。</span><span class="sxs-lookup"><span data-stu-id="96450-232">(Optional) You can configure the mail flow rule to apply encryption and custom branding.</span></span> <span data-ttu-id="96450-233">From **Do the following,** select **Modify the message security,** and then choose **Apply Office 365 Message Encryption and rights protection**.</span><span class="sxs-lookup"><span data-stu-id="96450-233">From **Do the following**, select **Modify the message security**, and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="96450-234">一覧から RMS テンプレートを選択し、[保存]**を選択して\*\*\*\*、[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="96450-234">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
   <span data-ttu-id="96450-235">テンプレートの一覧には、既定のテンプレートとオプション、および作成するカスタム テンプレートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="96450-235">The list of templates includes default templates and options and any custom templates you create.</span></span> <span data-ttu-id="96450-236">リストが空の場合は、新しい機能を使用して Office 365 Message Encryption を設定してください。</span><span class="sxs-lookup"><span data-stu-id="96450-236">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities.</span></span> <span data-ttu-id="96450-237">手順については [、「Set up new Office 365 Message Encryption capabilities 」を参照してください](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="96450-237">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="96450-238">既定のテンプレートの詳細については、「Azure Information Protection 用のテンプレートの構成と [管理」を参照してください](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="96450-238">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="96450-239">転送しないオプション **の詳細については、メール** の転送 [を行う前にオプションを参照してください](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="96450-239">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="96450-240">暗号化専用オプションの詳細 **については、「** メールの暗号化 [のみ」オプションを参照してください](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="96450-240">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="96450-241">別 **のアクションを** 指定する場合は、[アクションの追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="96450-241">Choose **add action** if you want to specify another action.</span></span>

## <a name="background-color-reference"></a><span data-ttu-id="96450-242">背景色の参照</span><span class="sxs-lookup"><span data-stu-id="96450-242">Background color reference</span></span>

<span data-ttu-id="96450-243">背景色に使用できる色の名前は制限されています。</span><span class="sxs-lookup"><span data-stu-id="96450-243">The color names that you can use for the background color are limited.</span></span> <span data-ttu-id="96450-244">色の名前の代わりに、16 進コード値 (#RRGGBB) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="96450-244">Instead of a color name, you can use a hex code value (#RRGGBB).</span></span> <span data-ttu-id="96450-245">色の名前に対応する 16 進コード値を使用するか、ユーザー設定の 16 進コード値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="96450-245">You can use a hex code value that corresponds to a color name, or you can use a custom hex code value.</span></span> <span data-ttu-id="96450-246">必ず 16 進数のコード値を二重引用符 (たとえば) で囲んでください `"#f0f8ff"` 。</span><span class="sxs-lookup"><span data-stu-id="96450-246">Be sure to enclose the hex code value in quotation marks (for example, `"#f0f8ff"`).</span></span>

<span data-ttu-id="96450-247">使用可能な背景色の名前と対応する 16 進コードの値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="96450-247">The available background color names and their corresponding hex code values are described in the following table.</span></span>

|||
|---|---|
|<span data-ttu-id="96450-248">**色の名前**</span><span class="sxs-lookup"><span data-stu-id="96450-248">**Color name**</span></span>|<span data-ttu-id="96450-249">**カラー コード**</span><span class="sxs-lookup"><span data-stu-id="96450-249">**Color code**</span></span>|
|`aliceblue`|<span data-ttu-id="96450-250">#f0f8ff</span><span class="sxs-lookup"><span data-stu-id="96450-250">#f0f8ff</span></span>|
|`antiquewhite`|<span data-ttu-id="96450-251">#faebd7</span><span class="sxs-lookup"><span data-stu-id="96450-251">#faebd7</span></span>|
|`aqua`|<span data-ttu-id="96450-252">#00ffff</span><span class="sxs-lookup"><span data-stu-id="96450-252">#00ffff</span></span>|
|`aquamarine`|<span data-ttu-id="96450-253">#7fffd4</span><span class="sxs-lookup"><span data-stu-id="96450-253">#7fffd4</span></span>|
|`azure`|<span data-ttu-id="96450-254">#f0ffff</span><span class="sxs-lookup"><span data-stu-id="96450-254">#f0ffff</span></span>|
|`beige`|<span data-ttu-id="96450-255">#f5f5dc</span><span class="sxs-lookup"><span data-stu-id="96450-255">#f5f5dc</span></span>|
|`bisque`|<span data-ttu-id="96450-256">#ffe4c4</span><span class="sxs-lookup"><span data-stu-id="96450-256">#ffe4c4</span></span>|
|`black`|<span data-ttu-id="96450-257">#000000</span><span class="sxs-lookup"><span data-stu-id="96450-257">#000000</span></span>|
|`blanchedalmond`|<span data-ttu-id="96450-258">#ffebcd</span><span class="sxs-lookup"><span data-stu-id="96450-258">#ffebcd</span></span>|
|`blue`|<span data-ttu-id="96450-259">#0000ff</span><span class="sxs-lookup"><span data-stu-id="96450-259">#0000ff</span></span>|
|`blueviolet`|<span data-ttu-id="96450-260">#8a2be2</span><span class="sxs-lookup"><span data-stu-id="96450-260">#8a2be2</span></span>|
|`brown`|<span data-ttu-id="96450-261">#a52a2a</span><span class="sxs-lookup"><span data-stu-id="96450-261">#a52a2a</span></span>|
|`burlywood`|<span data-ttu-id="96450-262">#deb887</span><span class="sxs-lookup"><span data-stu-id="96450-262">#deb887</span></span>|
|`cadetblue`|<span data-ttu-id="96450-263">#5f9ea0</span><span class="sxs-lookup"><span data-stu-id="96450-263">#5f9ea0</span></span>|
|`chartreuse`|<span data-ttu-id="96450-264">#7fff00</span><span class="sxs-lookup"><span data-stu-id="96450-264">#7fff00</span></span>|
|`chocolate`|<span data-ttu-id="96450-265">#d2691e</span><span class="sxs-lookup"><span data-stu-id="96450-265">#d2691e</span></span>|
|`coral`|<span data-ttu-id="96450-266">#ff7f50</span><span class="sxs-lookup"><span data-stu-id="96450-266">#ff7f50</span></span>|
|`cornflowerblue`|<span data-ttu-id="96450-267">#6495ed</span><span class="sxs-lookup"><span data-stu-id="96450-267">#6495ed</span></span>|
|`cornsilk`|<span data-ttu-id="96450-268">#fff8dc</span><span class="sxs-lookup"><span data-stu-id="96450-268">#fff8dc</span></span>|
|`crimson`|<span data-ttu-id="96450-269">#dc143c</span><span class="sxs-lookup"><span data-stu-id="96450-269">#dc143c</span></span>|
|`cyan`|<span data-ttu-id="96450-270">#00ffff</span><span class="sxs-lookup"><span data-stu-id="96450-270">#00ffff</span></span>|
|`darkblue`|<span data-ttu-id="96450-271">#00008b</span><span class="sxs-lookup"><span data-stu-id="96450-271">#00008b</span></span>|
|`darkcyan`|<span data-ttu-id="96450-272">#008b8b</span><span class="sxs-lookup"><span data-stu-id="96450-272">#008b8b</span></span>|
|`darkgoldenrod`|<span data-ttu-id="96450-273">#b8860b</span><span class="sxs-lookup"><span data-stu-id="96450-273">#b8860b</span></span>|
|`darkgray`|<span data-ttu-id="96450-274">#a9a9a9</span><span class="sxs-lookup"><span data-stu-id="96450-274">#a9a9a9</span></span>|
|`darkgreen`|<span data-ttu-id="96450-275">#006400</span><span class="sxs-lookup"><span data-stu-id="96450-275">#006400</span></span>|
|`darkkhaki`|<span data-ttu-id="96450-276">#bdb76b</span><span class="sxs-lookup"><span data-stu-id="96450-276">#bdb76b</span></span>|
|`darkmagenta`|<span data-ttu-id="96450-277">#8b008b</span><span class="sxs-lookup"><span data-stu-id="96450-277">#8b008b</span></span>|
|`darkolivegreen`|<span data-ttu-id="96450-278">#556b2f</span><span class="sxs-lookup"><span data-stu-id="96450-278">#556b2f</span></span>|
|`darkorange`|<span data-ttu-id="96450-279">#ff8c00</span><span class="sxs-lookup"><span data-stu-id="96450-279">#ff8c00</span></span>|
|`darkorchid`|<span data-ttu-id="96450-280">#9932cc</span><span class="sxs-lookup"><span data-stu-id="96450-280">#9932cc</span></span>|
|`darkred`|<span data-ttu-id="96450-281">#8b0000</span><span class="sxs-lookup"><span data-stu-id="96450-281">#8b0000</span></span>|
|`darksalmon`|<span data-ttu-id="96450-282">#e9967a</span><span class="sxs-lookup"><span data-stu-id="96450-282">#e9967a</span></span>|
|`darkseagreen`|<span data-ttu-id="96450-283">#8fbc8f</span><span class="sxs-lookup"><span data-stu-id="96450-283">#8fbc8f</span></span>|
|`darkslateblue`|<span data-ttu-id="96450-284">#483d8b</span><span class="sxs-lookup"><span data-stu-id="96450-284">#483d8b</span></span>|
|`darkslategray`|<span data-ttu-id="96450-285">#2f4f4f</span><span class="sxs-lookup"><span data-stu-id="96450-285">#2f4f4f</span></span>|
|`darkturquoise`|<span data-ttu-id="96450-286">#00ced1</span><span class="sxs-lookup"><span data-stu-id="96450-286">#00ced1</span></span>|
|`darkviolet`|<span data-ttu-id="96450-287">#9400d3</span><span class="sxs-lookup"><span data-stu-id="96450-287">#9400d3</span></span>|
|`deeppink`|<span data-ttu-id="96450-288">#ff1493</span><span class="sxs-lookup"><span data-stu-id="96450-288">#ff1493</span></span>|
|`deepskyblue`|<span data-ttu-id="96450-289">#00bfff</span><span class="sxs-lookup"><span data-stu-id="96450-289">#00bfff</span></span>|
|`dimgray`|<span data-ttu-id="96450-290">#696969</span><span class="sxs-lookup"><span data-stu-id="96450-290">#696969</span></span>|
|`dodgerblue`|<span data-ttu-id="96450-291">#1e90ff</span><span class="sxs-lookup"><span data-stu-id="96450-291">#1e90ff</span></span>|
|`firebrick`|<span data-ttu-id="96450-292">#b22222</span><span class="sxs-lookup"><span data-stu-id="96450-292">#b22222</span></span>|
|`floralwhite`|<span data-ttu-id="96450-293">#fffaf0</span><span class="sxs-lookup"><span data-stu-id="96450-293">#fffaf0</span></span>|
|`forestgreen`|<span data-ttu-id="96450-294">#228b22</span><span class="sxs-lookup"><span data-stu-id="96450-294">#228b22</span></span>|
|`fuchsia`|<span data-ttu-id="96450-295">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="96450-295">#ff00ff</span></span>|
|`gainsboro`|<span data-ttu-id="96450-296">#dcdcdc</span><span class="sxs-lookup"><span data-stu-id="96450-296">#dcdcdc</span></span>|
|`ghostwhite`|<span data-ttu-id="96450-297">#f8f8ff</span><span class="sxs-lookup"><span data-stu-id="96450-297">#f8f8ff</span></span>|
|`gold`|<span data-ttu-id="96450-298">#ffd700</span><span class="sxs-lookup"><span data-stu-id="96450-298">#ffd700</span></span>|
|`goldenrod`|<span data-ttu-id="96450-299">#daa520</span><span class="sxs-lookup"><span data-stu-id="96450-299">#daa520</span></span>|
|`gray`|<span data-ttu-id="96450-300">#808080</span><span class="sxs-lookup"><span data-stu-id="96450-300">#808080</span></span>|
|`green`|<span data-ttu-id="96450-301">#008000</span><span class="sxs-lookup"><span data-stu-id="96450-301">#008000</span></span>|
|`greenyellow`|<span data-ttu-id="96450-302">#adff2f</span><span class="sxs-lookup"><span data-stu-id="96450-302">#adff2f</span></span>|
|`honeydew`|<span data-ttu-id="96450-303">#f0fff0</span><span class="sxs-lookup"><span data-stu-id="96450-303">#f0fff0</span></span>|
|`hotpink`|<span data-ttu-id="96450-304">#ff69b4</span><span class="sxs-lookup"><span data-stu-id="96450-304">#ff69b4</span></span>|
|`indianred`|<span data-ttu-id="96450-305">#cd5c5c</span><span class="sxs-lookup"><span data-stu-id="96450-305">#cd5c5c</span></span>|
|`indigo`|<span data-ttu-id="96450-306">#4b0082</span><span class="sxs-lookup"><span data-stu-id="96450-306">#4b0082</span></span>|
|`ivory`|<span data-ttu-id="96450-307">#fffff0</span><span class="sxs-lookup"><span data-stu-id="96450-307">#fffff0</span></span>|
|`khaki`|<span data-ttu-id="96450-308">#f0e68c</span><span class="sxs-lookup"><span data-stu-id="96450-308">#f0e68c</span></span>|
|`lavender`|<span data-ttu-id="96450-309">#e6e6fa</span><span class="sxs-lookup"><span data-stu-id="96450-309">#e6e6fa</span></span>|
|`lavenderblush`|<span data-ttu-id="96450-310">#fff0f5</span><span class="sxs-lookup"><span data-stu-id="96450-310">#fff0f5</span></span>|
|`lawngreen`|<span data-ttu-id="96450-311">#7cfc00</span><span class="sxs-lookup"><span data-stu-id="96450-311">#7cfc00</span></span>|
|`lemonchiffon`|<span data-ttu-id="96450-312">#fffacd</span><span class="sxs-lookup"><span data-stu-id="96450-312">#fffacd</span></span>|
|`lightblue`|<span data-ttu-id="96450-313">#add8e6</span><span class="sxs-lookup"><span data-stu-id="96450-313">#add8e6</span></span>|
|`lightcoral`|<span data-ttu-id="96450-314">#f08080</span><span class="sxs-lookup"><span data-stu-id="96450-314">#f08080</span></span>|
|`lightcyan`|<span data-ttu-id="96450-315">#e0ffff</span><span class="sxs-lookup"><span data-stu-id="96450-315">#e0ffff</span></span>|
|`lightgoldenrodyellow`|<span data-ttu-id="96450-316">#fafad2</span><span class="sxs-lookup"><span data-stu-id="96450-316">#fafad2</span></span>|
|`lightgray`|<span data-ttu-id="96450-317">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="96450-317">#d3d3d3</span></span>|
|`lightgrey`|<span data-ttu-id="96450-318">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="96450-318">#d3d3d3</span></span>|
|`lightgreen`|<span data-ttu-id="96450-319">#90ee90</span><span class="sxs-lookup"><span data-stu-id="96450-319">#90ee90</span></span>|
|`lightpink`|<span data-ttu-id="96450-320">#ffb6c1</span><span class="sxs-lookup"><span data-stu-id="96450-320">#ffb6c1</span></span>|
|`lightsalmon`|<span data-ttu-id="96450-321">#ffa07a</span><span class="sxs-lookup"><span data-stu-id="96450-321">#ffa07a</span></span>|
|`lightseagreen`|<span data-ttu-id="96450-322">#20b2aa</span><span class="sxs-lookup"><span data-stu-id="96450-322">#20b2aa</span></span>|
|`lightskyblue`|<span data-ttu-id="96450-323">#87cefa</span><span class="sxs-lookup"><span data-stu-id="96450-323">#87cefa</span></span>|
|`lightslategray`|<span data-ttu-id="96450-324">#778899</span><span class="sxs-lookup"><span data-stu-id="96450-324">#778899</span></span>|
|`lightsteelblue`|<span data-ttu-id="96450-325">#b0c4de</span><span class="sxs-lookup"><span data-stu-id="96450-325">#b0c4de</span></span>|
|`lightyellow`|<span data-ttu-id="96450-326">#ffffe0</span><span class="sxs-lookup"><span data-stu-id="96450-326">#ffffe0</span></span>|
|`lime`|<span data-ttu-id="96450-327">#00ff00</span><span class="sxs-lookup"><span data-stu-id="96450-327">#00ff00</span></span>|
|`limegreen`|<span data-ttu-id="96450-328">#32cd32</span><span class="sxs-lookup"><span data-stu-id="96450-328">#32cd32</span></span>|
|`linen`|<span data-ttu-id="96450-329">#faf0e6</span><span class="sxs-lookup"><span data-stu-id="96450-329">#faf0e6</span></span>|
|`magenta`|<span data-ttu-id="96450-330">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="96450-330">#ff00ff</span></span>|
|`maroon`|<span data-ttu-id="96450-331">#800000</span><span class="sxs-lookup"><span data-stu-id="96450-331">#800000</span></span>|
|`mediumaquamarine`|<span data-ttu-id="96450-332">#66cdaa</span><span class="sxs-lookup"><span data-stu-id="96450-332">#66cdaa</span></span>|
|`mediumblue`|<span data-ttu-id="96450-333">#0000cd</span><span class="sxs-lookup"><span data-stu-id="96450-333">#0000cd</span></span>|
|`mediumorchid`|<span data-ttu-id="96450-334">#ba55d3</span><span class="sxs-lookup"><span data-stu-id="96450-334">#ba55d3</span></span>|
|`mediumpurple`|<span data-ttu-id="96450-335">#9370db</span><span class="sxs-lookup"><span data-stu-id="96450-335">#9370db</span></span>|
|`mediumseagreen`|<span data-ttu-id="96450-336">#3cb371</span><span class="sxs-lookup"><span data-stu-id="96450-336">#3cb371</span></span>|
|`mediumslateblue`|<span data-ttu-id="96450-337">#7b68ee</span><span class="sxs-lookup"><span data-stu-id="96450-337">#7b68ee</span></span>|
|`mediumspringgreen`|<span data-ttu-id="96450-338">#00fa9a</span><span class="sxs-lookup"><span data-stu-id="96450-338">#00fa9a</span></span>|
|`mediumturquoise`|<span data-ttu-id="96450-339">#48d1cc</span><span class="sxs-lookup"><span data-stu-id="96450-339">#48d1cc</span></span>|
|`mediumvioletred`|<span data-ttu-id="96450-340">#c71585</span><span class="sxs-lookup"><span data-stu-id="96450-340">#c71585</span></span>|
|`midnightblue`|<span data-ttu-id="96450-341">#191970</span><span class="sxs-lookup"><span data-stu-id="96450-341">#191970</span></span>|
|`mintcream`|<span data-ttu-id="96450-342">#f5fffa</span><span class="sxs-lookup"><span data-stu-id="96450-342">#f5fffa</span></span>|
|`mistyrose`|<span data-ttu-id="96450-343">#ffe4e1</span><span class="sxs-lookup"><span data-stu-id="96450-343">#ffe4e1</span></span>|
|`moccasin`|<span data-ttu-id="96450-344">#ffe4b5</span><span class="sxs-lookup"><span data-stu-id="96450-344">#ffe4b5</span></span>|
|`navajowhite`|<span data-ttu-id="96450-345">#ffdead</span><span class="sxs-lookup"><span data-stu-id="96450-345">#ffdead</span></span>|
|`navy`|<span data-ttu-id="96450-346">#000080</span><span class="sxs-lookup"><span data-stu-id="96450-346">#000080</span></span>|
|`oldlace`|<span data-ttu-id="96450-347">#fdf5e6</span><span class="sxs-lookup"><span data-stu-id="96450-347">#fdf5e6</span></span>|
|`olive`|<span data-ttu-id="96450-348">#808000</span><span class="sxs-lookup"><span data-stu-id="96450-348">#808000</span></span>|
|`olivedrab`|<span data-ttu-id="96450-349">#6b8e23</span><span class="sxs-lookup"><span data-stu-id="96450-349">#6b8e23</span></span>|
|`orange`|<span data-ttu-id="96450-350">#ffa500</span><span class="sxs-lookup"><span data-stu-id="96450-350">#ffa500</span></span>|
|`orangered`|<span data-ttu-id="96450-351">#ff4500</span><span class="sxs-lookup"><span data-stu-id="96450-351">#ff4500</span></span>|
|`orchid`|<span data-ttu-id="96450-352">#da70d6</span><span class="sxs-lookup"><span data-stu-id="96450-352">#da70d6</span></span>|
|`palegoldenrod`|<span data-ttu-id="96450-353">#eee8aa</span><span class="sxs-lookup"><span data-stu-id="96450-353">#eee8aa</span></span>|
|`palegreen`|<span data-ttu-id="96450-354">#98fb98</span><span class="sxs-lookup"><span data-stu-id="96450-354">#98fb98</span></span>|
|`paleturquoise`|<span data-ttu-id="96450-355">#afeeee</span><span class="sxs-lookup"><span data-stu-id="96450-355">#afeeee</span></span>|
|`palevioletred`|<span data-ttu-id="96450-356">#db7093</span><span class="sxs-lookup"><span data-stu-id="96450-356">#db7093</span></span>|
|`papayawhip`|<span data-ttu-id="96450-357">#ffefd5</span><span class="sxs-lookup"><span data-stu-id="96450-357">#ffefd5</span></span>|
|`peachpuff`|<span data-ttu-id="96450-358">#ffdab9</span><span class="sxs-lookup"><span data-stu-id="96450-358">#ffdab9</span></span>|
|`peru`|<span data-ttu-id="96450-359">#cd853f</span><span class="sxs-lookup"><span data-stu-id="96450-359">#cd853f</span></span>|
|`pink`|<span data-ttu-id="96450-360">#ffc0cb</span><span class="sxs-lookup"><span data-stu-id="96450-360">#ffc0cb</span></span>|
|`plum`|<span data-ttu-id="96450-361">#dda0dd</span><span class="sxs-lookup"><span data-stu-id="96450-361">#dda0dd</span></span>|
|`powderblue`|<span data-ttu-id="96450-362">#b0e0e6</span><span class="sxs-lookup"><span data-stu-id="96450-362">#b0e0e6</span></span>|
|`purple`|<span data-ttu-id="96450-363">#800080</span><span class="sxs-lookup"><span data-stu-id="96450-363">#800080</span></span>|
|`red`|<span data-ttu-id="96450-364">#ff0000</span><span class="sxs-lookup"><span data-stu-id="96450-364">#ff0000</span></span>|
|`rosybrown`|<span data-ttu-id="96450-365">#bc8f8f</span><span class="sxs-lookup"><span data-stu-id="96450-365">#bc8f8f</span></span>|
|`royalblue`|<span data-ttu-id="96450-366">#4169e1</span><span class="sxs-lookup"><span data-stu-id="96450-366">#4169e1</span></span>|
|`saddlebrown`|<span data-ttu-id="96450-367">#8b4513</span><span class="sxs-lookup"><span data-stu-id="96450-367">#8b4513</span></span>|
|`salmon`|<span data-ttu-id="96450-368">#fa8072</span><span class="sxs-lookup"><span data-stu-id="96450-368">#fa8072</span></span>|
|`sandybrown`|<span data-ttu-id="96450-369">#f4a460</span><span class="sxs-lookup"><span data-stu-id="96450-369">#f4a460</span></span>|
|`seagreen`|<span data-ttu-id="96450-370">#00ff00</span><span class="sxs-lookup"><span data-stu-id="96450-370">#00ff00</span></span>|
|`seashell`|<span data-ttu-id="96450-371">#fff5ee</span><span class="sxs-lookup"><span data-stu-id="96450-371">#fff5ee</span></span>|
|`sienna`|<span data-ttu-id="96450-372">#a0522d</span><span class="sxs-lookup"><span data-stu-id="96450-372">#a0522d</span></span>|
|`silver`|<span data-ttu-id="96450-373">#c0c0c0</span><span class="sxs-lookup"><span data-stu-id="96450-373">#c0c0c0</span></span>|
|`skyblue`|<span data-ttu-id="96450-374">#87ceeb</span><span class="sxs-lookup"><span data-stu-id="96450-374">#87ceeb</span></span>|
|`slateblue`|<span data-ttu-id="96450-375">#6a5acd</span><span class="sxs-lookup"><span data-stu-id="96450-375">#6a5acd</span></span>|
|`slategray`|<span data-ttu-id="96450-376">#708090</span><span class="sxs-lookup"><span data-stu-id="96450-376">#708090</span></span>|
|`snow`|<span data-ttu-id="96450-377">#fffafa</span><span class="sxs-lookup"><span data-stu-id="96450-377">#fffafa</span></span>|
|`springgreen`|<span data-ttu-id="96450-378">#00ff7f</span><span class="sxs-lookup"><span data-stu-id="96450-378">#00ff7f</span></span>|
|`steelblue`|<span data-ttu-id="96450-379">#4682b4</span><span class="sxs-lookup"><span data-stu-id="96450-379">#4682b4</span></span>|
|`tan`|<span data-ttu-id="96450-380">#d2b48c</span><span class="sxs-lookup"><span data-stu-id="96450-380">#d2b48c</span></span>|
|`teal`|<span data-ttu-id="96450-381">#008080</span><span class="sxs-lookup"><span data-stu-id="96450-381">#008080</span></span>|
|`thistle`|<span data-ttu-id="96450-382">#d8bfd8</span><span class="sxs-lookup"><span data-stu-id="96450-382">#d8bfd8</span></span>|
|`tomato`|<span data-ttu-id="96450-383">#ff6347</span><span class="sxs-lookup"><span data-stu-id="96450-383">#ff6347</span></span>|
|`turquoise`|<span data-ttu-id="96450-384">#40e0d0</span><span class="sxs-lookup"><span data-stu-id="96450-384">#40e0d0</span></span>|
|`violet`|<span data-ttu-id="96450-385">#ee82ee</span><span class="sxs-lookup"><span data-stu-id="96450-385">#ee82ee</span></span>|
|`wheat`|<span data-ttu-id="96450-386">#f5deb3</span><span class="sxs-lookup"><span data-stu-id="96450-386">#f5deb3</span></span>|
|`white`|<span data-ttu-id="96450-387">#ffffff</span><span class="sxs-lookup"><span data-stu-id="96450-387">#ffffff</span></span>|
|`whitesmoke`|<span data-ttu-id="96450-388">#f5f5f5</span><span class="sxs-lookup"><span data-stu-id="96450-388">#f5f5f5</span></span>|
|`yellow`|<span data-ttu-id="96450-389">#ffff00</span><span class="sxs-lookup"><span data-stu-id="96450-389">#ffff00</span></span>|
|`yellowgreen`|<span data-ttu-id="96450-390">#9acd32</span><span class="sxs-lookup"><span data-stu-id="96450-390">#9acd32</span></span>|
