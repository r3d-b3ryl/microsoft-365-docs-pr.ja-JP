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
description: Microsoft 365 E5 または Microsoft 365 E5 セキュリティの安全なドキュメントについて説明します。
ms.openlocfilehash: 8918c7da26a60c7cfd64b7148d0added82cc6642
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949456"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="0bb66-103">Microsoft 365 E5 の安全なドキュメント</span><span class="sxs-lookup"><span data-stu-id="0bb66-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="0bb66-104">「安全なドキュメント」は、microsoft [Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) を使用して、 [保護ビュー](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)で開かれたドキュメントやファイルをスキャンする、microsoft 365 e5 または microsoft 365 E5 セキュリティの機能です。</span><span class="sxs-lookup"><span data-stu-id="0bb66-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0bb66-105">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="0bb66-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0bb66-106">Office バージョン 2004 (12730) を使用しているユーザーが、安全なドキュメントを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0bb66-106">Safe Documents is now generally available to users with Office Version 2004 (12730.x) or greater!</span></span> <span data-ttu-id="0bb66-107">この機能は既定でオフになっており、セキュリティ管理者が有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bb66-107">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="0bb66-108">この機能は、 *microsoft 365 E5* または *Microsoft 365 E5 セキュリティ* ライセンスを持つユーザーのみが使用できます (Office 365 ATP プランには含まれていません)。</span><span class="sxs-lookup"><span data-stu-id="0bb66-108">This feature is only available to users with the *Microsoft 365 E5* or *Microsoft 365 E5 Security* license (not included in Office 365 ATP plans).</span></span>

- <span data-ttu-id="0bb66-109">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bb66-109">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0bb66-110">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bb66-110">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0bb66-111">詳細情報</span><span class="sxs-lookup"><span data-stu-id="0bb66-111">For more information about</span></span> 

- <span data-ttu-id="0bb66-112">このトピックの手順を実行するには、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bb66-112">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="0bb66-113">安全なドキュメントを有効にして構成するには、組織の **管理** 役割グループまたは **セキュリティ管理者** 役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bb66-113">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="0bb66-114">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0bb66-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="0bb66-115">Microsoft はどのようにデータを処理していますか?</span><span class="sxs-lookup"><span data-stu-id="0bb66-115">How does Microsoft handle your data?</span></span>

<span data-ttu-id="0bb66-116">保護された状態を維持するために、安全なドキュメントは、分析のために [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) クラウドにファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="0bb66-116">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span>

- <span data-ttu-id="0bb66-117">Microsoft Defender Advanced Threat Protection がデータをどのように処理するかの詳細については、 [こちら](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bb66-117">Details on how Microsoft Defender Advanced Threat Protection handles your data can be found [here](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>
- <span data-ttu-id="0bb66-118">上記のガイドラインに加えて、安全なドキュメントによって送信されたファイルは、分析に必要な時間を超えて (通常は24時間未満)、Defender に保持されません。</span><span class="sxs-lookup"><span data-stu-id="0bb66-118">In addition to the guidelines above, files sent by Safe Documents are not retained in Defender beyond the time needed for analysis, which is typically less than 24 hours.</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="0bb66-119">セキュリティ & コンプライアンスセンターを使用して安全なドキュメントを構成する</span><span class="sxs-lookup"><span data-stu-id="0bb66-119">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="0bb66-120">のセキュリティ & コンプライアンスセンター] を開き <https://protection.office.com> ます。</span><span class="sxs-lookup"><span data-stu-id="0bb66-120">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="0bb66-121">[ **脅威管理** \> **ポリシー** \> **ATP 安全な添付ファイル**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0bb66-121">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="0bb66-122">[ **Office アプリケーションで保護されたビューの外部で開くファイルを信頼する** ] セクションで、次のどちらかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="0bb66-122">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="0bb66-123">**Office クライアントの安全なドキュメントを有効にする**</span><span class="sxs-lookup"><span data-stu-id="0bb66-123">**Turn on Safe Documents for Office clients**</span></span>

   - <span data-ttu-id="0bb66-124">**安全なドキュメントが悪意のあるファイルを識別している場合でも、保護されたビューのクリックをユーザーに許可**します。このオプションは有効にしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0bb66-124">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="0bb66-125">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0bb66-125">When you're finished, click **Save**.</span></span>

![ATP の「安全な添付ファイル」ページ](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a><span data-ttu-id="0bb66-127">Exchange Online の PowerShell またはスタンドアロンの EOP PowerShell を使用して安全なドキュメントを構成する</span><span class="sxs-lookup"><span data-stu-id="0bb66-127">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="0bb66-128">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="0bb66-128">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="0bb66-129">_Enablesafedocs_パラメーターは、組織全体に対して安全なドキュメントを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="0bb66-129">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="0bb66-130">_Allowsafedocsopen_パラメーターを使用すると、ドキュメントが悪意のあるものとして識別された場合に、保護されたビュー (ドキュメントを開く操作) をユーザーが終了できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0bb66-130">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="0bb66-131">この例では、組織全体に対して安全なドキュメントを有効にし、保護されたビューから悪意があると識別されたドキュメントをユーザーが開くことができないようにします。</span><span class="sxs-lookup"><span data-stu-id="0bb66-131">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="0bb66-132">構文およびパラメーターの詳細については、「 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bb66-132">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="0bb66-133">設定が適用されたことを確認する方法</span><span class="sxs-lookup"><span data-stu-id="0bb66-133">How do I know this worked?</span></span>

<span data-ttu-id="0bb66-134">安全なドキュメントを有効にして構成したことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0bb66-134">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="0bb66-135">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル**] に移動して、[ **Office アプリケーションの外部で保護されたビューの外部で開くファイルを信頼する際** に、ユーザーが安全に実行できるようにする] セクションの選択内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="0bb66-135">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="0bb66-136">Exchange Online PowerShell で次のコマンドを実行し、プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="0bb66-136">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
