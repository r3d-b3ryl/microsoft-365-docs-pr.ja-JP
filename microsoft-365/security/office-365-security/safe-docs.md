---
title: Office 365 ATP の安全なドキュメント
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Microsoft 365 E5 または Microsoft 365 E5 Security の安全なドキュメントについて説明します。
ms.openlocfilehash: cd689099fc6a6caa1e0e649c3f152f1de123bf12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827471"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="c51f3-103">Microsoft 365 E5 の安全なドキュメント</span><span class="sxs-lookup"><span data-stu-id="c51f3-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="c51f3-104">安全なドキュメントは、Microsoft 365 E5 または Microsoft 365 E5 セキュリティの機能です。 [この機能は、保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) ビューで開かれていたドキュメントやファイルを Microsoft Defender Advanced Threat Protection [を使用してスキャンします](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)。</span><span class="sxs-lookup"><span data-stu-id="c51f3-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c51f3-105">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c51f3-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c51f3-106">安全なドキュメントは、通常、Office バージョン 2004 (12730.x) 以上のユーザーから入手可能になります。</span><span class="sxs-lookup"><span data-stu-id="c51f3-106">Safe Documents is now generally available to users with Office Version 2004 (12730.x) or greater!</span></span> <span data-ttu-id="c51f3-107">この機能は既定でオフになっており、セキュリティ管理者が有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c51f3-107">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="c51f3-108">この機能は *、Microsoft 365 E5 または Microsoft 365* E5 セキュリティ ライセンス (Office *365* ATP プランには含まれていません) を持つユーザーのみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="c51f3-108">This feature is only available to users with the *Microsoft 365 E5* or *Microsoft 365 E5 Security* license (not included in Office 365 ATP plans).</span></span>

- <span data-ttu-id="c51f3-109">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c51f3-109">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c51f3-110">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c51f3-110">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c51f3-111">このトピックの手順を実行する場合は、あかじにアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c51f3-111">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="c51f3-112">安全なドキュメントを有効にして構成するには、組織の管理役割グループまたは **セキュリティ管理者役割グループ** の **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="c51f3-112">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="c51f3-113">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c51f3-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="c51f3-114">Microsoft はおデータをどのように処理しますか?</span><span class="sxs-lookup"><span data-stu-id="c51f3-114">How does Microsoft handle your data?</span></span>

<span data-ttu-id="c51f3-115">保護された安全なドキュメントは、Microsoft Defender Advanced [Threat Protection クラウドに分析用に](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="c51f3-115">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span>

- <span data-ttu-id="c51f3-116">Microsoft Defender Advanced Threat Protection によるデータの処理方法について詳しくは、こちらを参照 [してください。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="c51f3-116">Details on how Microsoft Defender Advanced Threat Protection handles your data can be found [here](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span></span>
- <span data-ttu-id="c51f3-117">上記のガイドラインに加えて、「安全なドキュメントから送信されたファイル」は、通常、24 時間未満の時間を超えて Defender に保持されません。</span><span class="sxs-lookup"><span data-stu-id="c51f3-117">In addition to the guidelines above, files sent by Safe Documents are not retained in Defender beyond the time needed for analysis, which is typically less than 24 hours</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="c51f3-118">セキュリティ コンプライアンス センターを&を使用して安全なドキュメントを構成する</span><span class="sxs-lookup"><span data-stu-id="c51f3-118">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="c51f3-119">[監視] & [インストール] を開きます <https://protection.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="c51f3-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="c51f3-120">脅威管理**ポリシー** \> **Policy** \> **の ATP の安全な添付ファイルに移動します**。</span><span class="sxs-lookup"><span data-stu-id="c51f3-120">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="c51f3-121">[Office **アプリケーションの保護ビュー] セクションの保護ビュー以外ではファイルを開くことがファイルを信頼しても安全な状態を保つため、次** のどちらかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c51f3-121">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="c51f3-122">**アクセス クライアントの「安全なドキュメント」Officeオンにする**</span><span class="sxs-lookup"><span data-stu-id="c51f3-122">**Turn on Safe Documents for Office clients**</span></span>

   - <span data-ttu-id="c51f3-123">**「安全なドキュメント」が悪意のあるファイルとして**識別されている場合でも、保護ビューでのユーザーのクリックを許可します。 このオプションは有効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="c51f3-123">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="c51f3-124">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c51f3-124">When you're finished, click **Save**.</span></span>

![ATP の安全な添付ファイル ページ](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a><span data-ttu-id="c51f3-126">Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用して安全なドキュメントを構成する</span><span class="sxs-lookup"><span data-stu-id="c51f3-126">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="c51f3-127">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="c51f3-127">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="c51f3-128">_EnableSafeDocs パラメーターは_、組織全体の安全なドキュメントを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="c51f3-128">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="c51f3-129">_AllowSafeDocsOpen パラメーターを_指定すると、ユーザーが保護ビューを開く操作 (つまり、ドキュメントを開く) を禁止するかどうかを指定できます (ドキュメントは、悪意があると特定された場合)。</span><span class="sxs-lookup"><span data-stu-id="c51f3-129">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="c51f3-130">この例では、組織全体に対して安全なドキュメントを有効にし、ユーザーが悪意のあることが特定されたドキュメントを保護ビューから開くことがないようにします。</span><span class="sxs-lookup"><span data-stu-id="c51f3-130">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="c51f3-131">構文およびパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="c51f3-131">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="c51f3-132">設定が適用されたことを確認する方法</span><span class="sxs-lookup"><span data-stu-id="c51f3-132">How do I know this worked?</span></span>

<span data-ttu-id="c51f3-133">安全なドキュメントの有効化と構成が完了したことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c51f3-133">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="c51f3-134">セキュリティ & コンプライアンス センターでは、脅 **威管理** \> **ポリシー** \> **ATP の安全な添付ファイル**に移動し、ファイルが信頼して Office アプリケーションの保護ビュー セクション以外で開くときも、ヘルプユーザーが安全 **に選択した内容を保管します** 。</span><span class="sxs-lookup"><span data-stu-id="c51f3-134">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="c51f3-135">Exchange Online PowerShell で次のコマンドを実行し、プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="c51f3-135">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
