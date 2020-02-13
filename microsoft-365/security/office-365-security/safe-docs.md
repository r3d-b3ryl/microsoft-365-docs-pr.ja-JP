---
title: Office 365 ATP の安全なドキュメント
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Office 365 ATP の安全なドキュメントについて説明します。
ms.openlocfilehash: db73fc152a5a580a28bf6d8424ebc2a139cf3303
ms.sourcegitcommit: c2a36b16e354e20db5fd6275175ca856eae55bfc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2020
ms.locfileid: "41960355"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a><span data-ttu-id="ad276-103">Office の安全なドキュメント 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ad276-103">Safe Documents in Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="ad276-104">「安全なドキュメント」は、 [Microsoft Defender Advanced threat](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) protection (ATP) を使用して、[保護さ](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)れたビューで開かれたドキュメントやファイルをスキャンする Office 365 advanced threat protection (ATP) の機能です。</span><span class="sxs-lookup"><span data-stu-id="ad276-104">Safe Documents is a feature in Office 365 Advanced Threat Protection (ATP) that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ad276-105">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="ad276-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ad276-106">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad276-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ad276-107">Exchange Online Protection PowerShell に接続するには、「 [Exchange Online protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad276-107">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ad276-108">このトピックの手順を実行するには、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad276-108">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="ad276-109">安全なドキュメントを有効にして構成するには、組織の**管理**役割グループまたは**セキュリティ管理者**役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad276-109">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="ad276-110">セキュリティ & コンプライアンスセンターの役割グループの詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad276-110">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-office-365-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="ad276-111">Office 365 セキュリティ & コンプライアンスセンターを使用して安全なドキュメントを構成する</span><span class="sxs-lookup"><span data-stu-id="ad276-111">Use the Office 365 Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="ad276-112">にある<https://protection.office.com>Office 365 セキュリティ & コンプライアンスセンターを開きます。</span><span class="sxs-lookup"><span data-stu-id="ad276-112">Open the Office 365 Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="ad276-113">[**脅威管理** \> **ポリシー** \> **ATP 安全な添付ファイル**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ad276-113">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="ad276-114">[ **Office アプリケーションで保護されたビューの外部で開くファイルを信頼する**] セクションで、次のどちらかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ad276-114">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="ad276-115">**Office クライアントに対して安全なドキュメントを有効にする (詳細な分析のためにファイルは Microsoft Cloud にも送信されます)**</span><span class="sxs-lookup"><span data-stu-id="ad276-115">**Turn on Safe Documents for Office clients (Files will also be sent to Microsoft Cloud for deep analyses)**</span></span>

   - <span data-ttu-id="ad276-116">**安全なドキュメントが悪意のあるファイルを識別している場合でも、保護されたビューのクリックをユーザーに許可**します。このオプションは有効にしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ad276-116">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="ad276-117">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad276-117">When you're finished, click **Save**.</span></span>

![ATP の「安全な添付ファイル」ページ](../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-safe-documents"></a><span data-ttu-id="ad276-119">Exchange Online PowerShell または Exchange Online Protection PowerShell を使用して安全なドキュメントを構成する</span><span class="sxs-lookup"><span data-stu-id="ad276-119">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="ad276-120">次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="ad276-120">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- <span data-ttu-id="ad276-121">_Enablesafedocs_パラメーターは、組織全体に対して安全なドキュメントを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="ad276-121">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="ad276-122">_Allowsafedocsopen_パラメーターを使用すると、ドキュメントが悪意のあるものとして識別された場合に、保護されたビュー (ドキュメントを開く操作) をユーザーが終了できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad276-122">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="ad276-123">この例では、組織全体に対して安全なドキュメントを有効にし、保護されたビューから悪意があると識別されたドキュメントをユーザーが開くことができないようにします。</span><span class="sxs-lookup"><span data-stu-id="ad276-123">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="ad276-124">構文およびパラメーターの詳細については、「 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad276-124">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="ad276-125">設定が適用されたことを確認する方法</span><span class="sxs-lookup"><span data-stu-id="ad276-125">How do I know this worked?</span></span>

<span data-ttu-id="ad276-126">安全なドキュメントを有効にして構成したことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad276-126">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="ad276-127">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル**] に移動して、[ **Office アプリケーションの外部で保護されたビューの外部で開くファイルを信頼する際**に、ユーザーが安全に実行できるようにする] セクションの選択内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="ad276-127">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="ad276-128">Exchange Online PowerShell で次のコマンドを実行し、プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="ad276-128">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
