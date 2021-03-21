---
title: Microsoft 365 の秘密度ラベルで暗号化されたドキュメントの共同編集を有効にする
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
description: デスクトップ アプリで共同編集と自動保存を有効にする設定をオンにして、SharePoint、OneDrive でドキュメントのラベル付けと暗号化が行えます。
ms.openlocfilehash: 90c00eb448d6d8f02170a37062af05cb0c0db59d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919573"
---
# <a name="enable-co-authoring-for-files-encrypted-with-sensitivity-labels"></a><span data-ttu-id="6aaeb-103">機密度ラベルを使用して暗号化されたファイルの共同編集を有効にする</span><span class="sxs-lookup"><span data-stu-id="6aaeb-103">Enable co-authoring for files encrypted with sensitivity labels</span></span>

><span data-ttu-id="6aaeb-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="6aaeb-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="6aaeb-105">この機能は現在プレビュー段階であり、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-105">This feature is in preview and subject to change.</span></span> 
>
> <span data-ttu-id="6aaeb-106">次の理由により、運用テナントではなくテスト テナントでこの機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-106">Enable this feature in a test tenant rather than a production tenant because:</span></span>
> - <span data-ttu-id="6aaeb-107">この機能でラベルのメタデータが変更しますが、現在一部のプラットフォームのアプリではこの変更をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-107">This feature makes changes to labeling metadata and not all apps on all platforms currently support this change</span></span>
> - <span data-ttu-id="6aaeb-108">この機能を有効にしたら、自分でこの機能を無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-108">You cannot disable this feature yourself after it is enabled</span></span>

<span data-ttu-id="6aaeb-109">Office デスクトップ アプリで [共同編集](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) をサポートする設定を有効にして、ドキュメントが [秘密度レベル](sensitivity-labels.md) でラベル付け、暗号化されている場合、複数のユーザーがこれらのドキュメントを同時に編集できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-109">Enable the setting to support [co-authoring](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) for Office desktop apps so that when documents are labeled and encrypted by [sensitivity labels](sensitivity-labels.md), multiple users can edit these documents at the same time.</span></span>

<span data-ttu-id="6aaeb-110">テナントに対してこの設定が有効になっていないと、ユーザーが Office デスクトップ アプリを使用する度に SharePoint または OneDrive にある暗号化ドキュメントを確認しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-110">Without this setting enabled for your tenant, users must check out an encrypted document stored in SharePoint or OneDrive when they use Office desktop apps.</span></span> <span data-ttu-id="6aaeb-111">そのため、リアルタイムで共同作業を行うことができません。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-111">As a result, they can't collaborate in real time.</span></span> <span data-ttu-id="6aaeb-112">または、[SharePoint と OneDrive にある Office ファイルが秘密度レベルでラベル付けされている場合には](sensitivity-labels-sharepoint-onedrive-files.md)、ユーザーは Office on the web を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-112">Or, they must use Office on the web when [sensitivity labels are enabled for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

<span data-ttu-id="6aaeb-113">さらに、この機能を有効にすると、これらのラベル付きおよび暗号化されたファイルで[自動保存](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5)機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-113">In addition, enabling this functionality results in the [AutoSave](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) functionality being supported for these labeled and encrypted files.</span></span>

<span data-ttu-id="6aaeb-114">リリースの発表を確認するには、「[Microsoft Information Protection で暗号化されたドキュメントとラベルの更新に関する共同編集の発表](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-co-authoring-on-microsoft-information-protection/ba-p/2164162)」に関するブログ投稿を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-114">To read the release announcement, see the blog post [Announcing co-authoring on Microsoft Information Protection-encrypted documents and labeling updates](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-co-authoring-on-microsoft-information-protection/ba-p/2164162).</span></span>

## <a name="metadata-changes-for-sensitivity-labels"></a><span data-ttu-id="6aaeb-115">機密度ラベル用のメタデータ変更</span><span class="sxs-lookup"><span data-stu-id="6aaeb-115">Metadata changes for sensitivity labels</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6aaeb-116">共同編集の設定を有効にすると、暗号化されていないファイルのラベル情報はカスタム プロパティに保存されません。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-116">After you enable the setting for co-authoring, labeling information for unencrypted files is no longer saved in custom properties.</span></span>
> 
> <span data-ttu-id="6aaeb-117">ラベルのメタデータを使用しない場所へ読み書きするアプリ、サービス、スクリプト、またはツールを使用する場合は、この設定を有効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-117">Do not enable this setting if you use any apps, services, scripts, or tools that reads or writes labeling metadata to the old location.</span></span>

<span data-ttu-id="6aaeb-118">Office デスクトップ アプリの共同編集をサポートする設定を有効にする前に、この操作によって Office ファイルに保存され、そこから読み取ることがあるラベル付けメタデータが変更する点を把握していることが重要です。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-118">Before you enable the setting to support co-authoring for Office desktop apps, it's important to understand that this action makes changes to the labeling metadata that is saved to and read from Office files.</span></span>

<span data-ttu-id="6aaeb-119">ラベルのメタデータには、お使いのテナント、適用した機密度ラベルを特定する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-119">The labeling metadata includes information that identifies your tenant and applied sensitivity label.</span></span> <span data-ttu-id="6aaeb-120">この設定による変更は、Word、Excel、PowerPoint 用の暗号化されていないファイルのメタデータ形式と場所です。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-120">The change that this setting makes is the metadata format and location for unencrypted files for Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="6aaeb-121">暗号化されたファイルやメールにはメタデータのラベル付けによる変更はありません。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-121">There are no labeling metadata changes for encrypted files or emails.</span></span>

<span data-ttu-id="6aaeb-122">この変更は新しくラベル付けされたファイルと、既にラベルが付いているファイルの両方に影響します。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-122">This change affects both files that are newly labeled and files that are already labeled.</span></span> <span data-ttu-id="6aaeb-123">共同編集設定をサポートするアプリとサービスを使用する場合:</span><span class="sxs-lookup"><span data-stu-id="6aaeb-123">When you use apps and services that support the co-authoring setting:</span></span>
- <span data-ttu-id="6aaeb-124">新しくラベル付けされたファイルには、新しい形式と場所だけをメタデータのラベル付けに使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-124">For files that are newly labeled, only the new format and location is used for the labeling metadata.</span></span>
- <span data-ttu-id="6aaeb-125">既にラベルが付いているファイルには、次にファイルを開いて保存する場合で、ファイルに使用しない形式と場所のメタデータがある場合には、新しい形式と場所にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-125">For files that are already labeled, the next time the file is opened and saved, if the file has metadata in the old format and location, it is copied to the new format and location.</span></span>

<span data-ttu-id="6aaeb-126">このメタデータの変更の詳細については、次のリソースを参照できます。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-126">You can read more about this metadata change from the following resources:</span></span>

- <span data-ttu-id="6aaeb-127">ブログ投稿: [Upcoming Changes to Microsoft Information Protection Metadata Storage](https://techcommunity.microsoft.com/t5/microsoft-security-and/upcoming-changes-to-microsoft-information-protection-metadata/ba-p/1904418)</span><span class="sxs-lookup"><span data-stu-id="6aaeb-127">Blog post: [Upcoming Changes to Microsoft Information Protection Metadata Storage](https://techcommunity.microsoft.com/t5/microsoft-security-and/upcoming-changes-to-microsoft-information-protection-metadata/ba-p/1904418)</span></span>

- <span data-ttu-id="6aaeb-128">オープン仕様: [2.6.3 LabelInfo とユーザー設定のドキュメントのプロパティ]](/openspecs/office_file_formats/ms-offcrypto/13939de6-c833-44ab-b213-e0088bf02341)</span><span class="sxs-lookup"><span data-stu-id="6aaeb-128">Open Specifications: [2.6.3 LabelInfo versus Custom Document Properties](/openspecs/office_file_formats/ms-offcrypto/13939de6-c833-44ab-b213-e0088bf02341)</span></span>

<span data-ttu-id="6aaeb-129">これらの変このため、ラベルのメタデータを使用しない場所へ読み書きするアプリ、サービス、スクリプト、またはツールが組織内にある場合は、この設定を有効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-129">Because of these changes, do not enable this setting if you have any apps, services, scripts, or tools in your organization that reads or writes labeling metadata to the old location.</span></span> <span data-ttu-id="6aaeb-130">有効にした場合には、サンプルのような結果になることがあります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-130">If you do, some example consequences:</span></span>

- <span data-ttu-id="6aaeb-131">ラベル付きドキュメントが、ユーザーにはラベル無しと表示される</span><span class="sxs-lookup"><span data-stu-id="6aaeb-131">A document that is labeled appears to users to be unlabeled</span></span>

- <span data-ttu-id="6aaeb-132">ユーザーにドキュメントで使用されていないラベルが表示される</span><span class="sxs-lookup"><span data-stu-id="6aaeb-132">A document displays an out-of-date label to users</span></span>

- <span data-ttu-id="6aaeb-133">ラベル付け、暗号化されたドキュメントの共同編集と自動保存は、別のユーザーが新しいラベル付きメタデータをサポートしない Office デスクトップ アプリでドキュメントを開いている場合は機能しません。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-133">Co-authoring and AutoSave won't work for a labeled and encrypted document if another user has it open in an Office desktop app that doesn't support the new labeling metadata</span></span>

- <span data-ttu-id="6aaeb-134">[Office 添付ファイルでカスタム プロパティとしてラベルを識別する](/azure/information-protection/configure-exo-rules#example-2-rule-that-applies-the-encrypt-only-option-to-emails-when-they-have-attachments-that-are-labeled-confidential--partners-and-these-emails-are-sent-outside-the-organization) Exchange Online のメール フロー ルールでは、メールや添付ファイルを暗号化できなくなるか、間違って暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-134">An Exchange Online mail flow rule that [identifies labels as custom properties in Office attachments](/azure/information-protection/configure-exo-rules#example-2-rule-that-applies-the-encrypt-only-option-to-emails-when-they-have-attachments-that-are-labeled-confidential--partners-and-these-emails-are-sent-outside-the-organization) fails to encrypt the email and attachment, or incorrectly encrypts them</span></span>

<span data-ttu-id="6aaeb-135">この設定とラベルのメタデータの変更をサポートするアプリとサービスの一覧は、次のセクションを確認します。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-135">Check the following section for a list of apps and services that support this setting and the changes to the labeling metadata.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6aaeb-136">前提条件</span><span class="sxs-lookup"><span data-stu-id="6aaeb-136">Prerequisites</span></span>

<span data-ttu-id="6aaeb-137">この機能を有効にする前に、次の前提条件を必ず把握します。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-137">Make sure you understand the following prerequisites before you turn on this feature.</span></span>

- <span data-ttu-id="6aaeb-138">このプレビューではテスト テナントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-138">You must use a test tenant for this preview.</span></span>

- <span data-ttu-id="6aaeb-139">この機能を有効にする場合は、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-139">You must be a global admin to turn on this feature.</span></span>

- <span data-ttu-id="6aaeb-140">テナントに対して、[SharePoint、OneDrive で Office ファイル](sensitivity-labels-sharepoint-onedrive-files.md) への秘密度レベルを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-140">Sensitivity labels must be [enabled for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) for the tenant.</span></span> <span data-ttu-id="6aaeb-141">この機能が有効になっていない場合、秘密度レベルがあるファイルへの共同編集を有効にする設定を選択すると、自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-141">If this feature isn't already enabled, it will be automatically enabled when you select the setting to turn on co-authoring for files with sensitivity labels.</span></span>

- <span data-ttu-id="6aaeb-142">Microsoft 365 Apps for enterprise:</span><span class="sxs-lookup"><span data-stu-id="6aaeb-142">Microsoft 365 Apps for enterprise:</span></span>
    - <span data-ttu-id="6aaeb-143">**Windows**: 最小ビルド 16.0.13801.20182 の [現在のチャネル (プレビュー)](https://office.com/insider) または最小ビルド 16.0.13819.20006 の [ベータ チャネル](https://office.com/insider)</span><span class="sxs-lookup"><span data-stu-id="6aaeb-143">**Windows**: [Current Channel (Preview)](https://office.com/insider) with minimum build 16.0.13801.20182, or [Beta Channel](https://office.com/insider) with minimum build 16.0.13819.20006</span></span>
    - <span data-ttu-id="6aaeb-144">**macOS**: 最小ビルド 16.47.218.0 の [ベータ チャンネル](https://office.com/insider)</span><span class="sxs-lookup"><span data-stu-id="6aaeb-144">**macOS**: [Beta Channel](https://office.com/insider) with minimal build 16.47.218.0</span></span>
    - <span data-ttu-id="6aaeb-145">**iOS**: まだサポートされていません</span><span class="sxs-lookup"><span data-stu-id="6aaeb-145">**iOS**: Not yet supported</span></span>
    - <span data-ttu-id="6aaeb-146">**Android**: まだサポートされていません</span><span class="sxs-lookup"><span data-stu-id="6aaeb-146">**Android**: Not yet supported</span></span>

- <span data-ttu-id="6aaeb-147">テナント内のすべてのアプリ、サービス、および運用ツールで、新しい[メタデータのラベル付け](#metadata-changes-for-sensitivity-labels)をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-147">All apps, services, and operational tools in your tenant must support the new [labeling metadata](#metadata-changes-for-sensitivity-labels).</span></span> <span data-ttu-id="6aaeb-148">次のいずれかを使用する場合は、必要な最小バージョンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-148">If you use any of the following, check the minimum versions required:</span></span>
    
    - <span data-ttu-id="6aaeb-149">**Azure Information Protection 統合ラベル付けクライアントとスキャナー:**</span><span class="sxs-lookup"><span data-stu-id="6aaeb-149">**Azure Information Protection unified labeling client and scanner:**</span></span>
        - <span data-ttu-id="6aaeb-150">[Microsoft ダウンロード センター](https://www.microsoft.com/en-us/download/details.aspx?id=53018)からインストールできるパブリック プレビュー バージョン (AzInfoProtection_2.10.46_CoAuthoring_PublicPreview.exe のインストール名)</span><span class="sxs-lookup"><span data-stu-id="6aaeb-150">A public preview version (installation name of AzInfoProtection_2.10.46_CoAuthoring_PublicPreview.exe) that you can install from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=53018)</span></span>
    
    - <span data-ttu-id="6aaeb-151">**Windows 用または macOS 用の OneDrive 同期アプリ:**</span><span class="sxs-lookup"><span data-stu-id="6aaeb-151">**OneDrive sync app for Windows or macOS:**</span></span>
        - <span data-ttu-id="6aaeb-152">最小バージョン 19.002.0121.0008</span><span class="sxs-lookup"><span data-stu-id="6aaeb-152">Minimum version of 19.002.0121.0008</span></span>
    
    - <span data-ttu-id="6aaeb-153">**エンドポイント データ損失防止 (Endpoint DLP):**</span><span class="sxs-lookup"><span data-stu-id="6aaeb-153">**Endpoint data loss prevention (Endpoint DLP):**</span></span>
        - <span data-ttu-id="6aaeb-154">Windows 10 version 1809 (KB 4601383)</span><span class="sxs-lookup"><span data-stu-id="6aaeb-154">Windows 10 1809 with KB 4601383</span></span>
        - <span data-ttu-id="6aaeb-155">Windows 10 version 1903, version 1909 (KB 4601380)</span><span class="sxs-lookup"><span data-stu-id="6aaeb-155">Windows 10 1903 and 1909 with KB 4601380</span></span>
        - <span data-ttu-id="6aaeb-156">Windows 10 version 2004 (KB 4601382)</span><span class="sxs-lookup"><span data-stu-id="6aaeb-156">Windows 10 2004 with KB 4601382</span></span>
    
    - <span data-ttu-id="6aaeb-157">**Microsoft Information Protection SDK を使用するアプリとサービス:**</span><span class="sxs-lookup"><span data-stu-id="6aaeb-157">**Apps and services that use the Microsoft Information Protection SDK:**</span></span> 
        - <span data-ttu-id="6aaeb-158">最小バージョン 1.7</span><span class="sxs-lookup"><span data-stu-id="6aaeb-158">Minimum version of 1.7</span></span> 

<span data-ttu-id="6aaeb-159">この機能を有効にすると、Microsoft 365 サービスで自動的に新しいラベルのメタデータがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-159">Microsoft 365 services automatically support the new labeling metadata when you turn on this feature.</span></span> <span data-ttu-id="6aaeb-160">例えば:</span><span class="sxs-lookup"><span data-stu-id="6aaeb-160">For example:</span></span>

- [<span data-ttu-id="6aaeb-161">自動ラベル作成ポリシー</span><span class="sxs-lookup"><span data-stu-id="6aaeb-161">Auto-labeling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)
- [<span data-ttu-id="6aaeb-162">秘密度レベルを条件として使用する DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="6aaeb-162">DLP policies that use sensitivity labels as conditions</span></span>](dlp-sensitivity-label-as-condition.md)
- [<span data-ttu-id="6aaeb-163">秘密度レベルの適用が構成されている Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6aaeb-163">Microsoft Cloud App Security configured to apply sensitivity labels</span></span>](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)

## <a name="limitations"></a><span data-ttu-id="6aaeb-164">制限事項</span><span class="sxs-lookup"><span data-stu-id="6aaeb-164">Limitations</span></span>

<span data-ttu-id="6aaeb-165">秘密度ラベルで暗号化されたファイル共同編集設定をテナントに対して有効にする前に、この機能の以下の制限事項を必ず把握します。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-165">Before you enable the tenant setting for co-authoring for files encrypted with sensitivity labels, make sure you understand the following limitations of this feature.</span></span>

- <span data-ttu-id="6aaeb-166">[メタデータのラベル付けの変更](#metadata-changes-for-sensitivity-labels)により、テナントのすべてのアプリ、サービス、運用ツールで新しいラベル メタデータをサポートして、一貫性のある信頼性の高いラベル付けを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-166">Because of the [labeling metadata changes](#metadata-changes-for-sensitivity-labels), all apps, services, and operational tools in your tenant must support the new labeling metadata for a consistent and reliable labeling experience.</span></span>
    
    <span data-ttu-id="6aaeb-167">Excel での仕様: 誰かが秘密度ラベルのメタデータの変更をサポートしない Excel のバージョンを使用してファイルを編集、保存すると、暗号化を適用しない秘密度ラベルのメタデータは、そのファイルから削除されることがあります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-167">Specific to Excel: Metadata for a sensitivity label that doesn't apply encryption can be deleted from a file if somebody edits and saves that file by using a version of Excel that doesn't support the metadata changes for sensitivity labels.</span></span>

- <span data-ttu-id="6aaeb-168">共同編集と自動保存は、次の [暗号化用の構成](encryption-sensitivity-labels.md#configure-encryption-settings) のどれかを使用する Office ドキュメントのラベル付けと暗号化へはサポートされず、使用もできません。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-168">Co-authoring and AutoSave aren't supported and don't work for labeled and encrypted Office documents that use any of the following [configurations for encryption](encryption-sensitivity-labels.md#configure-encryption-settings):</span></span>
    - <span data-ttu-id="6aaeb-169">**ラベルを適用する場合にユーザーがアクセス許可を割り当てられ**、**Word、PowerPoint、Excel でユーザーにアクセス許可を指定するように求める** のチェックボックスが選択されています。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-169">**Let users assign permissions when they apply the label** and the checkbox **In Word, PowerPoint, and Excel, prompt users to specify permissions** is selected.</span></span> <span data-ttu-id="6aaeb-170">この構成は、"ユーザー定義のアクセス許可" と呼ばれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-170">This configuration is sometimes referred to as "user-defined permissions".</span></span>
    - <span data-ttu-id="6aaeb-171">**コンテンツへのユーザー アクセスは有効期限が切れています** は、**[使用しない]** 以外の値が設定されています。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-171">**User access to content expires** is set to a value other than **Never**.</span></span>
    - <span data-ttu-id="6aaeb-172">**二重キー暗号化** が選択されています。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-172">**Double Key Encryption** is selected.</span></span>
    
    <span data-ttu-id="6aaeb-173">これらの暗号化構成のどれかを使用したラベルは Office アプリで表示されます。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-173">For labels with any of these encryption configurations, the labels display in Office apps.</span></span> <span data-ttu-id="6aaeb-174">ただし、ユーザーがこれらのラベルを選択し、他のユーザーがドキュメントを編集していない場合、共同編集と自動保存を使用できないという警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-174">However, when users select these labels and nobody else is editing the document, they are warned that co-authoring and AutoSave won't be available.</span></span> <span data-ttu-id="6aaeb-175">他のユーザーがドキュメントを編集している場合は、ラベルを適用できないというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-175">If somebody else is editing the document, users see a message that the labels can't be applied.</span></span>

- <span data-ttu-id="6aaeb-176">Azure Information Protection 統合ラベル付けクライアントを使用する場合: [その他の要件または制限](/azure/information-protection/known-issues#known-issues-for-co-authoring-public-preview)については、このラベル付けクライアントのドキュメントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-176">If you use the Azure Information Protection unified labeling client: Check the documentation for this labeling client for [more requirements or limitations](/azure/information-protection/known-issues#known-issues-for-co-authoring-public-preview).</span></span>

## <a name="known-issues-for-this-preview"></a><span data-ttu-id="6aaeb-177">このプレビューでの既知の問題</span><span class="sxs-lookup"><span data-stu-id="6aaeb-177">Known issues for this preview</span></span>

<span data-ttu-id="6aaeb-178">機密度ラベルで暗号化されたファイルを共同編集しているこのプレビュー バージョンでは、次の既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-178">This preview version of co-authoring for files encrypted with sensitivity labels has the following known issues:</span></span>

- <span data-ttu-id="6aaeb-179">Office for the web で 300 MB 以上の Word ファイル、Excel ファイル、PowerPoint ファイルにラベルを適用できない。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-179">Users won't be able to apply any labels in Office for the web for Word, Excel, and PowerPoint files that are bigger than 300 MB.</span></span> <span data-ttu-id="6aaeb-180">これらのファイルでは、Office デスクトップ アプリを使用してラベルを適用できますが、ファイルを開いているのが自分だけである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-180">For these files, you can use the Office desktop apps to apply a label but you must be the only person who has the file open.</span></span>

- <span data-ttu-id="6aaeb-181">[秘密度レベルを条件として使用する DLP ポリシー](dlp-sensitivity-label-as-condition.md) を使用する場合、暗号化されていないメールへの添付ファイルはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-181">When you use [DLP policies that use sensitivity labels as conditions](dlp-sensitivity-label-as-condition.md), unencrypted attachments for emails are not supported.</span></span>

- <span data-ttu-id="6aaeb-182">iOS 用 Office アプリと Android 用 Office アプリがサポートされていない。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-182">Office apps for iOS and Android are not supported.</span></span>

## <a name="how-to-enable-co-authoring-for-files-with-sensitivity-labels"></a><span data-ttu-id="6aaeb-183">機密度ラベルを使用したファイルの共同編集を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="6aaeb-183">How to enable co-authoring for files with sensitivity labels</span></span>

> [!CAUTION]
> <span data-ttu-id="6aaeb-184">この設定をオンにできるのは、一方向の操作によります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-184">Turning on this setting is a one-way action.</span></span> <span data-ttu-id="6aaeb-185">この機能がプレビュー中には、メタデータの変更、前提条件、制限事項、このページに記載されている既知の問題を確認して理解した上で、非稼働環境でのみテストを行ってください。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-185">While the feature is in preview, test it only in a non-production environment and only after you have read and understood the metadata changes, prerequisites, limitations, and any known issues documented on this page.</span></span>

<span data-ttu-id="6aaeb-186">プレビュー中には、特定の URL を使用して、Microsoft 365 コンプライアンス センターのこの設定にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-186">During the preview, you must use a specific URL to access this setting in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="6aaeb-187">次のリンクを使用して、テスト テナントのグローバル管理者として Microsoft 365 コンプライアンス センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-187">Sign in to the Microsoft 365 compliance center as a global admin for your test tenant, using the following link:</span></span>
    
    ```http
    https://compliance.microsoft.com/co-authoring_for_files_with_sensitivity_labels
    ```
    <span data-ttu-id="6aaeb-188">このリンクで、直接テナント設定の **機密度ラベルを使用したファイルの共同編集** にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-188">This link takes you directly to the tenant setting, **Co-authoring for files with sensitivity labels**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6aaeb-189">続行する前に、ユーザーへの影響がないテスト テナントにサインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-189">Before you continue, check you're signed in to a test tenant that won't affect your users:</span></span> 
    >
    > <span data-ttu-id="6aaeb-190">コンプライアンス センターの上部右にあるアカウント イニシャルのある円を選択し、テナント名に目的のテスト テナントが表示されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-190">Select the circle with your account initials in the top right of the compliance center, and confirm that the tenant name does display your intended test tenant.</span></span>
    
2. <span data-ttu-id="6aaeb-191">概要の説明、前提条件、予想される内容、さらにこの設定をオンにした後は設定を戻すことができないという警告を読みます。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-191">Read the summary description, prerequisites, what to expect, and the warning that you can't turn off this setting after you've turned it on.</span></span> <span data-ttu-id="6aaeb-192">**機密度ラベルを使用したファイルの共同編集を有効にする** を選んでから **適用** を選びます。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-192">Then select **Turn on co-authoring for files with sensitivity labels**, and **Apply**:</span></span>
    
    ![機密度ラベルを使用したファイルの共同編集をオンにできるオプション](../media/co-authoring-tenant-option-for-sensitivity-labels.png)

3. <span data-ttu-id="6aaeb-194">この設定が環境全体に複製されるのを 24 時間待ってから、この共同編集用の新機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-194">Wait 24 hours for this setting to replicate across your environment before you test this new feature for co-authoring.</span></span>

## <a name="contact-support-if-you-need-to-disable-this-feature"></a><span data-ttu-id="6aaeb-195">この機能を無効にする必要がある場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-195">Contact Support if you need to disable this feature</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6aaeb-196">この機能を無効にする必要がある場合、ラベル情報が失われることがあります。ご注意ください。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-196">If you do need to disable this feature, be aware that labeling information can be lost.</span></span>

<span data-ttu-id="6aaeb-197">テナントに対して機密度ラベルを使用したファイルの共同編集を有効にすると、自身ではこの設定を無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-197">After you've enabled co-authoring for files with sensitivity labels for your tenant, you can't disable this setting yourself.</span></span> <span data-ttu-id="6aaeb-198">そのため、この前提条件、結果、制限事項を確認して理解した上でこの設定を有効にすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-198">That's why it's so important that you check and understand the prerequisites, consequences, and limitations before you enable this setting.</span></span> <span data-ttu-id="6aaeb-199">また、これがこの機能を運用テナントではなくテスト テナントでテストするようにお勧めする理由でもあります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-199">It's also why we recommend that you test this feature with a test tenant rather than a production tenant.</span></span>

![共同編集で機密度ラベルが有効になっていることを表示させるオプション](../media/co-authoring-tenant-option-set-for-sensitivity-labels.png)

<span data-ttu-id="6aaeb-201">スクリーンショットからでもわかるように、この設定がオンになっている場合は [Microsoft サポート](/office365/admin/contact-support-for-business-products) に問い合わせてこの設定を無効にするようにリクエストできます。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-201">As you see from the screenshot when this setting has been turned on, you can contact [Microsoft Support](/office365/admin/contact-support-for-business-products) and request to turn off this setting.</span></span> <span data-ttu-id="6aaeb-202">このリクエストには数日かかる場合があり、テナントのグローバル管理者であることを証明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-202">This request might take several days and you will need to prove that you are a global administrator for your tenant.</span></span> <span data-ttu-id="6aaeb-203">通常のサポート料金が適用されることをご了承ください。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-203">Expect usual support charges to apply.</span></span> 

<span data-ttu-id="6aaeb-204">サポート エンジニアがテナントに対してこの設定を無効にした場合:</span><span class="sxs-lookup"><span data-stu-id="6aaeb-204">If a support engineer disables this setting for your tenant:</span></span>

- <span data-ttu-id="6aaeb-205">新しいラベルのメタデータをサポートするアプリとサービスには、ラベルが読み取りまたは保存された元のメタデータ形式と場所に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-205">For apps and services that support the new labeling metadata, they now revert to the original metadata format and location when labels are read or saved.</span></span>

- <span data-ttu-id="6aaeb-206">この設定を有効にしていた間に使用された Office ドキュメントの新しいメタデータ形式と場所は、元の形式と場所にはコピーされません。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-206">The new metadata format and location for Office documents that were used while the setting was enabled will not be copied to the original format and location.</span></span> <span data-ttu-id="6aaeb-207">そのため、暗号化されていない Word、Excel、PowerPoint のファイルに関するこのラベル情報は失われます。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-207">As a result, this labeling information for unencrypted Word, Excel, and PowerPoint files will be lost.</span></span>

- <span data-ttu-id="6aaeb-208">テナントでは共同編集と自動保存が機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-208">Co-authoring and AutoSave no longer work in your tenant.</span></span>

- <span data-ttu-id="6aaeb-209">OneDrive、SharePoint の Office ファイルへの機密度ラベルは有効なままです。</span><span class="sxs-lookup"><span data-stu-id="6aaeb-209">Sensitivity labels remain enabled for Office files in OneDrive and SharePoint.</span></span>