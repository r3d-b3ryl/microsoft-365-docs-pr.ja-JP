---
title: データ ガバナンスの推奨事項のためのコンテンツの識別方法
ms.author: brendonb
author: stephow-MSFT
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Office 365 セキュリティ/コンプライアンス センターは、組織の現在の設定に基づきデータ ガバナンスのための推奨事項を提供し、ユーザーによる設定作業を簡略化します。これらの推奨事項の一部は組織で特定のコンテンツを検出し、そのコンテンツを管理するための推奨手順を提供します。たとえば、重要な業務コンテンツ (弁護士依頼人間の秘匿特権や秘密保持契約書に関わる情報など) を含むアイテムが推奨事項によって検出された際に、ユーザーは保持ラベルを自動適用し、必要に応じてアイテムを機密扱いにして保持することができます。このトピックでは、ユーザーに表示される可能性があるデータ ガバナンスの推奨事項を一覧表示し、それぞれの推奨事項をトリガーするコンテンツについて説明します。
ms.openlocfilehash: 3d96b7c15d5b6a0f6ec3bbf467bd8a1099af559a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37085204"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="6c4ba-106">データ ガバナンスの推奨事項のためのコンテンツの識別方法</span><span class="sxs-lookup"><span data-stu-id="6c4ba-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="6c4ba-p102">Office 365 セキュリティ/コンプライアンス センターは、組織の現在の設定に基づきデータ ガバナンスのための推奨事項を提供し、ユーザーによる設定作業を簡略化します。これらの推奨事項の一部は組織で特定のコンテンツを検出し、そのコンテンツを管理するための推奨手順を提供します。たとえば、重要な業務コンテンツ (弁護士依頼人間の秘匿特権や秘密保持契約書に関わる情報など) を含むアイテムが推奨事項によって検出された際に、ユーザーは保持ラベルを自動適用し、必要に応じてアイテムを機密扱いにして保持することができます。</span><span class="sxs-lookup"><span data-stu-id="6c4ba-p102">The Office 365 Security & Compliance Center provides recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they’re classified and retained as needed.</span></span>

<span data-ttu-id="6c4ba-110">このトピックでは、ユーザーに表示される可能性があるデータ ガバナンスの推奨事項を一覧表示し、それぞれの推奨事項をトリガーするコンテンツについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6c4ba-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="6c4ba-111">ボイスメールのクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="6c4ba-111">Clean up voicemail</span></span>

<span data-ttu-id="6c4ba-p103">この推奨事項は、メッセージの種類が “ボイスメール” と識別されるメール メッセージがユーザーのメールボックスで検出されたときに表示されます。詳細については、「[Exchange でのメッセージのプロパティ](https://docs.microsoft.com/ja-JP/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c4ba-p103">This recommendation appears when email messages identified as the message type ‘voicemail’ are detected in users’ mailboxes. Learn more about [message properties in Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="6c4ba-114">弁護士/依頼人特権関連コンテンツのラベル付け</span><span class="sxs-lookup"><span data-stu-id="6c4ba-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="6c4ba-115">この推奨事項は、次のいずれかの条件が満たされた場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c4ba-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="6c4ba-116">メール メッセージの本文で、これらのキーワードのいずれの組み合わせも検出されます。</span><span class="sxs-lookup"><span data-stu-id="6c4ba-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="6c4ba-117">ACP</span><span class="sxs-lookup"><span data-stu-id="6c4ba-117">ACP</span></span>
    - <span data-ttu-id="6c4ba-118">弁護士依頼人特権</span><span class="sxs-lookup"><span data-stu-id="6c4ba-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="6c4ba-119">弁護士/依頼人特権</span><span class="sxs-lookup"><span data-stu-id="6c4ba-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="6c4ba-120">弁護士/依頼人特権がある</span><span class="sxs-lookup"><span data-stu-id="6c4ba-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="6c4ba-121">SharePoint ファイルまたは OneDrive ファイルで、これらのキーワードのいずれの組み合わせも検出されます</span><span class="sxs-lookup"><span data-stu-id="6c4ba-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="6c4ba-122">ACP</span><span class="sxs-lookup"><span data-stu-id="6c4ba-122">ACP</span></span>
    - <span data-ttu-id="6c4ba-123">弁護士依頼人特権\*</span><span class="sxs-lookup"><span data-stu-id="6c4ba-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="6c4ba-124">AC 特権</span><span class="sxs-lookup"><span data-stu-id="6c4ba-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="6c4ba-125">オーディオ ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="6c4ba-125">Retain audio files</span></span>

<span data-ttu-id="6c4ba-126">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c4ba-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="6c4ba-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="6c4ba-127">.MP3</span></span>
- <span data-ttu-id="6c4ba-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="6c4ba-128">.WMA</span></span>
- <span data-ttu-id="6c4ba-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="6c4ba-129">.WAV</span></span>
- <span data-ttu-id="6c4ba-130">.RA</span><span class="sxs-lookup"><span data-stu-id="6c4ba-130">.RA</span></span>
- <span data-ttu-id="6c4ba-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="6c4ba-131">.RAM</span></span>
- <span data-ttu-id="6c4ba-132">.RM</span><span class="sxs-lookup"><span data-stu-id="6c4ba-132">.RM</span></span>
- <span data-ttu-id="6c4ba-133">.MID</span><span class="sxs-lookup"><span data-stu-id="6c4ba-133">.MID</span></span>
- <span data-ttu-id="6c4ba-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="6c4ba-134">.OGG</span></span>
- <span data-ttu-id="6c4ba-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="6c4ba-135">.AIFF</span></span>
- <span data-ttu-id="6c4ba-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="6c4ba-136">.PCM</span></span>
- <span data-ttu-id="6c4ba-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="6c4ba-137">.AAC</span></span>
- <span data-ttu-id="6c4ba-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="6c4ba-138">.FLAC</span></span>
- <span data-ttu-id="6c4ba-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="6c4ba-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="6c4ba-140">CAD ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="6c4ba-140">Retain CAD files</span></span>

<span data-ttu-id="6c4ba-141">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c4ba-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="6c4ba-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="6c4ba-142">.3DXML</span></span>
- <span data-ttu-id="6c4ba-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="6c4ba-143">.ACIS</span></span>
- <span data-ttu-id="6c4ba-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="6c4ba-144">.ARC</span></span>
- <span data-ttu-id="6c4ba-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="6c4ba-145">.ASM</span></span>
- <span data-ttu-id="6c4ba-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="6c4ba-146">.CAT\*</span></span>
- <span data-ttu-id="6c4ba-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="6c4ba-147">.CGR</span></span>
- <span data-ttu-id="6c4ba-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="6c4ba-148">.DW\*</span></span>
- <span data-ttu-id="6c4ba-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="6c4ba-149">.DX\*</span></span>
- <span data-ttu-id="6c4ba-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="6c4ba-150">.EDRW</span></span>
- <span data-ttu-id="6c4ba-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="6c4ba-151">.IAM</span></span>
- <span data-ttu-id="6c4ba-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="6c4ba-152">.IGES</span></span>
- <span data-ttu-id="6c4ba-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="6c4ba-153">.IGS</span></span>
- <span data-ttu-id="6c4ba-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="6c4ba-154">.IPT</span></span>
- <span data-ttu-id="6c4ba-155">.JT</span><span class="sxs-lookup"><span data-stu-id="6c4ba-155">.JT</span></span>
- <span data-ttu-id="6c4ba-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="6c4ba-156">.MF1</span></span>
- <span data-ttu-id="6c4ba-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="6c4ba-157">.NEU</span></span>
- <span data-ttu-id="6c4ba-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="6c4ba-158">.PAR</span></span>
- <span data-ttu-id="6c4ba-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="6c4ba-159">.PKG</span></span>
- <span data-ttu-id="6c4ba-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="6c4ba-160">.PRC</span></span>
- <span data-ttu-id="6c4ba-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="6c4ba-161">.PRT</span></span>
- <span data-ttu-id="6c4ba-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="6c4ba-162">.PSM</span></span>
- <span data-ttu-id="6c4ba-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="6c4ba-163">.PWD</span></span>
- <span data-ttu-id="6c4ba-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="6c4ba-164">.SLD\*</span></span>
- <span data-ttu-id="6c4ba-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="6c4ba-165">.STEP</span></span>
- <span data-ttu-id="6c4ba-166">.STL</span><span class="sxs-lookup"><span data-stu-id="6c4ba-166">.STL</span></span>
- <span data-ttu-id="6c4ba-167">.STP</span><span class="sxs-lookup"><span data-stu-id="6c4ba-167">.STP</span></span>
- <span data-ttu-id="6c4ba-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="6c4ba-168">.U3D</span></span>
- <span data-ttu-id="6c4ba-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="6c4ba-169">.UNV</span></span>
- <span data-ttu-id="6c4ba-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="6c4ba-170">.VRML</span></span>
- <span data-ttu-id="6c4ba-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="6c4ba-171">.WRL</span></span>
- <span data-ttu-id="6c4ba-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="6c4ba-172">.X_\*</span></span>
- <span data-ttu-id="6c4ba-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="6c4ba-173">.XAS</span></span>
- <span data-ttu-id="6c4ba-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="6c4ba-174">.XMT\*</span></span>
- <span data-ttu-id="6c4ba-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="6c4ba-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="6c4ba-176">画像ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="6c4ba-176">Retain image files</span></span>

<span data-ttu-id="6c4ba-177">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c4ba-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="6c4ba-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="6c4ba-178">.JPEG</span></span>
- <span data-ttu-id="6c4ba-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="6c4ba-179">.GIF</span></span>
- <span data-ttu-id="6c4ba-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="6c4ba-180">.TIF\*</span></span>
- <span data-ttu-id="6c4ba-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="6c4ba-181">.BMP</span></span>
- <span data-ttu-id="6c4ba-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="6c4ba-182">.PNG</span></span>
- <span data-ttu-id="6c4ba-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="6c4ba-183">.RAW</span></span>
- <span data-ttu-id="6c4ba-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="6c4ba-184">.PSD</span></span>
- <span data-ttu-id="6c4ba-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="6c4ba-185">.PSP</span></span>
- <span data-ttu-id="6c4ba-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="6c4ba-186">.JPG</span></span>
- <span data-ttu-id="6c4ba-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="6c4ba-187">.EXIF</span></span>
- <span data-ttu-id="6c4ba-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="6c4ba-188">.PPM</span></span>
- <span data-ttu-id="6c4ba-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="6c4ba-189">.PGM</span></span>
- <span data-ttu-id="6c4ba-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="6c4ba-190">.PBM</span></span>
- <span data-ttu-id="6c4ba-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="6c4ba-191">.PNM</span></span>
- <span data-ttu-id="6c4ba-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="6c4ba-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="6c4ba-193">NDA 関連コンテンツの保持</span><span class="sxs-lookup"><span data-stu-id="6c4ba-193">Retain NDA content</span></span> 

<span data-ttu-id="6c4ba-194">この推奨事項は、次のいずれかの条件が満たされた場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c4ba-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="6c4ba-195">メール メッセージの本文で、これらのキーワードのいずれの組み合わせも検出されます。</span><span class="sxs-lookup"><span data-stu-id="6c4ba-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="6c4ba-196">NDA</span><span class="sxs-lookup"><span data-stu-id="6c4ba-196">NDA</span></span>
    - <span data-ttu-id="6c4ba-197">“秘密保持契約”</span><span class="sxs-lookup"><span data-stu-id="6c4ba-197">“Non-Disclosure Agreement”</span></span>
    - <span data-ttu-id="6c4ba-198">“秘密保持契約”</span><span class="sxs-lookup"><span data-stu-id="6c4ba-198">“Non Disclosure Agreement”</span></span>

- <span data-ttu-id="6c4ba-199">SharePoint または OneDrive の .PDF または .DOC ファイルで、これらのキーワードのいずれの組み合わせも検出されます。</span><span class="sxs-lookup"><span data-stu-id="6c4ba-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="6c4ba-200">NDA</span><span class="sxs-lookup"><span data-stu-id="6c4ba-200">NDA</span></span>
    - <span data-ttu-id="6c4ba-201">“秘密保持契約”</span><span class="sxs-lookup"><span data-stu-id="6c4ba-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="6c4ba-202">ソフトウェア開発ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="6c4ba-202">Retain software development files</span></span>

<span data-ttu-id="6c4ba-203">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c4ba-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="6c4ba-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="6c4ba-204">.ASAX</span></span>
- <span data-ttu-id="6c4ba-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="6c4ba-205">.ASM</span></span>
- <span data-ttu-id="6c4ba-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="6c4ba-206">.ASP\*</span></span>
- <span data-ttu-id="6c4ba-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="6c4ba-207">.BAT</span></span>
- <span data-ttu-id="6c4ba-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="6c4ba-208">.CONFIG</span></span>
- <span data-ttu-id="6c4ba-209">.CS</span><span class="sxs-lookup"><span data-stu-id="6c4ba-209">.CS</span></span>
- <span data-ttu-id="6c4ba-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="6c4ba-210">.CSS</span></span>
- <span data-ttu-id="6c4ba-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="6c4ba-211">.DISCO</span></span>
- <span data-ttu-id="6c4ba-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="6c4ba-212">.HTM\*</span></span>
- <span data-ttu-id="6c4ba-213">.INC</span><span class="sxs-lookup"><span data-stu-id="6c4ba-213">.INC</span></span>
- <span data-ttu-id="6c4ba-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="6c4ba-214">.JAD</span></span>
- <span data-ttu-id="6c4ba-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="6c4ba-215">.JAVA</span></span>
- <span data-ttu-id="6c4ba-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="6c4ba-216">.JS\*</span></span>
- <span data-ttu-id="6c4ba-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="6c4ba-217">.LIB</span></span>
- <span data-ttu-id="6c4ba-218">.O</span><span class="sxs-lookup"><span data-stu-id="6c4ba-218">.O</span></span>
- <span data-ttu-id="6c4ba-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="6c4ba-219">.PHP</span></span>
- <span data-ttu-id="6c4ba-220">.RC</span><span class="sxs-lookup"><span data-stu-id="6c4ba-220">.RC</span></span>
- <span data-ttu-id="6c4ba-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="6c4ba-221">.RESX</span></span>
- <span data-ttu-id="6c4ba-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="6c4ba-222">.RPT</span></span>
- <span data-ttu-id="6c4ba-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="6c4ba-223">.RSS</span></span>
- <span data-ttu-id="6c4ba-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="6c4ba-224">.SCPT</span></span>
- <span data-ttu-id="6c4ba-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="6c4ba-225">.SRC</span></span>
- <span data-ttu-id="6c4ba-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="6c4ba-226">.VB\*</span></span>
- <span data-ttu-id="6c4ba-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="6c4ba-227">.WSF</span></span>
- <span data-ttu-id="6c4ba-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="6c4ba-228">.XCODEPROJ</span></span>
- <span data-ttu-id="6c4ba-229">.XML</span><span class="sxs-lookup"><span data-stu-id="6c4ba-229">.XML</span></span>
- <span data-ttu-id="6c4ba-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="6c4ba-230">.XSD</span></span>
- <span data-ttu-id="6c4ba-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="6c4ba-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="6c4ba-232">ビデオ ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="6c4ba-232">Retain video files</span></span>

<span data-ttu-id="6c4ba-233">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c4ba-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="6c4ba-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="6c4ba-234">.AVCHD</span></span>
- <span data-ttu-id="6c4ba-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="6c4ba-235">.AVI</span></span>
- <span data-ttu-id="6c4ba-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="6c4ba-236">.FLV</span></span>
- <span data-ttu-id="6c4ba-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="6c4ba-237">.MOV</span></span>
- <span data-ttu-id="6c4ba-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="6c4ba-238">.MP2V</span></span>
- <span data-ttu-id="6c4ba-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="6c4ba-239">.MP4</span></span>
- <span data-ttu-id="6c4ba-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="6c4ba-240">.MP4V</span></span>
- <span data-ttu-id="6c4ba-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="6c4ba-241">.MPE</span></span>
- <span data-ttu-id="6c4ba-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="6c4ba-242">.MPEG</span></span>
- <span data-ttu-id="6c4ba-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="6c4ba-243">.MPEG1</span></span>
- <span data-ttu-id="6c4ba-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="6c4ba-244">.MPEG2</span></span>
- <span data-ttu-id="6c4ba-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="6c4ba-245">.MPEG4</span></span>
- <span data-ttu-id="6c4ba-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="6c4ba-246">.MPG</span></span>
- <span data-ttu-id="6c4ba-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="6c4ba-247">.MPG2</span></span>
- <span data-ttu-id="6c4ba-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="6c4ba-248">.MPG4</span></span>
- <span data-ttu-id="6c4ba-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="6c4ba-249">.WMV</span></span>
- <span data-ttu-id="6c4ba-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="6c4ba-250">.XMV</span></span>
