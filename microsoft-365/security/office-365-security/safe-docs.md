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
ms.openlocfilehash: 5e91c226102d60368bf08b09ae5f0239f63599d5
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132223"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="7e063-103">Microsoft 365 E5 の安全なドキュメント</span><span class="sxs-lookup"><span data-stu-id="7e063-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="7e063-104">「安全なドキュメント」は、microsoft [Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) を使用して、 [保護ビュー](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)で開かれたドキュメントやファイルをスキャンする、microsoft 365 e5 または microsoft 365 E5 セキュリティの機能です。</span><span class="sxs-lookup"><span data-stu-id="7e063-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7e063-105">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="7e063-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7e063-106">セーフドキュメントは、 *microsoft 365 E5* または *Microsoft 365 E5 セキュリティ* ライセンスを持つユーザーのみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="7e063-106">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="7e063-107">これらのライセンスは、Office 365 Advanced Threat Protection (ATP) プランに含まれていません。</span><span class="sxs-lookup"><span data-stu-id="7e063-107">These licenses are not included in Office 365 Advanced Threat Protection (ATP) plans.</span></span>

- <span data-ttu-id="7e063-108"><https://protection.office.com> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="7e063-108">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="7e063-109">[ATP の安全な **添付ファイル** ] ページに直接移動するには、を開き <https://protection.office.com/safeattachmentv2> ます。</span><span class="sxs-lookup"><span data-stu-id="7e063-109">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="7e063-110">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e063-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="7e063-111">このトピックの手順を実行するには、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e063-111">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="7e063-112">安全なドキュメントを有効にして構成するには、組織の **管理** 役割グループまたは **セキュリティ管理者** 役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e063-112">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="7e063-113">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7e063-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="7e063-114">保護された状態を維持するために、安全なドキュメントは、分析のために [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) クラウドにファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="7e063-114">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="7e063-115">Microsoft Defender ATP がデータをどのように処理するかの詳細については、「 [Microsoft DEFENDER atp データの保存とプライバシー](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e063-115">Details on how Microsoft Defender ATP handles your data can be found here: [Microsoft Defender ATP data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

- <span data-ttu-id="7e063-116">Safe ドキュメントによって送信されたファイルは、分析に必要な時間 (通常は24時間未満) を超えて、Defender に保持されません。</span><span class="sxs-lookup"><span data-stu-id="7e063-116">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="7e063-117">セキュリティ & コンプライアンスセンターを使用して安全なドキュメントを構成する</span><span class="sxs-lookup"><span data-stu-id="7e063-117">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="7e063-118">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル**] に移動し、[ **グローバル設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e063-118">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="7e063-119">[ **グローバル設定** ] が表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="7e063-119">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="7e063-120">**Office クライアントに対して安全なドキュメントを有効**にします。トグルを右に移動して、機能をオンにします。オン ![ に ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) します。</span><span class="sxs-lookup"><span data-stu-id="7e063-120">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="7e063-121">**安全なドキュメントが悪意のあるファイルを識別している場合でも、保護されたビューのクリックをユーザーに許可**します。このオプションはオフのままにしておくことをお勧めします (トグルオフのままにし ![ ](../../media/scc-toggle-off.png) ます)。</span><span class="sxs-lookup"><span data-stu-id="7e063-121">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="7e063-122">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e063-122">When you're finished, click **Save**.</span></span>

   ![[ATP Safe Attachments] ページでグローバル設定を選択した後の、安全なドキュメントの設定。](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="7e063-124">Exchange Online PowerShell を使用して安全なドキュメントを構成する</span><span class="sxs-lookup"><span data-stu-id="7e063-124">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="7e063-125">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="7e063-125">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="7e063-126">_Enablesafedocs_パラメーターは、組織全体に対して安全なドキュメントを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="7e063-126">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="7e063-127">_Allowsafedocsopen_パラメーターを使用すると、ドキュメントが悪意のあるものとして識別された場合に、保護されたビュー (ドキュメントを開く操作) をユーザーが終了できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="7e063-127">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="7e063-128">この例では、組織全体に対して安全なドキュメントを有効にし、保護されたビューから悪意があると識別されたドキュメントをユーザーが開くことができないようにします。</span><span class="sxs-lookup"><span data-stu-id="7e063-128">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="7e063-129">構文およびパラメーターの詳細については、「 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e063-129">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="7e063-130">設定が適用されたことを確認する方法</span><span class="sxs-lookup"><span data-stu-id="7e063-130">How do I know this worked?</span></span>

<span data-ttu-id="7e063-131">安全なドキュメントを有効にして構成したことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7e063-131">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="7e063-132">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル**] に移動し、[**グローバル設定**] をクリックし、[ **Office クライアントの安全なドキュメントを有効**にする] をオンにして、**安全なドキュメントでファイルが悪意のある設定として識別される場合でも、[保護されたビューを使用してクリックできる**</span><span class="sxs-lookup"><span data-stu-id="7e063-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="7e063-133">Exchange Online PowerShell で次のコマンドを実行し、プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="7e063-133">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="7e063-134">次のファイルを使用して、安全なドキュメント保護をテストできます。</span><span class="sxs-lookup"><span data-stu-id="7e063-134">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="7e063-135">これらのドキュメントは、マルウェア対策およびウイルス対策ソリューションをテストするための EICAR.TXT ファイルに似ています。</span><span class="sxs-lookup"><span data-stu-id="7e063-135">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="7e063-136">これらのファイルは有害ではありませんが、安全なドキュメント保護をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="7e063-136">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="7e063-137">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="7e063-137">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="7e063-138">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="7e063-138">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="7e063-139">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="7e063-139">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
