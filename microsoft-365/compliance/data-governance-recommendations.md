---
title: データ ガバナンスの推奨事項のためのコンテンツの識別方法
ms.author: brendonb
author: laurawi
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
ms.openlocfilehash: 10752afb97fd0ae2993d88b4e3af9159d61de708
ms.sourcegitcommit: 1eecd7b127462585c35b0c96a179d37db45f6013
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "37342940"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="cebaf-106">データ ガバナンスの推奨事項のためのコンテンツの識別方法</span><span class="sxs-lookup"><span data-stu-id="cebaf-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="cebaf-p102">Office 365 セキュリティ/コンプライアンス センターは、組織の現在の設定に基づきデータ ガバナンスのための推奨事項を提供し、ユーザーによる設定作業を簡略化します。これらの推奨事項の一部は組織で特定のコンテンツを検出し、そのコンテンツを管理するための推奨手順を提供します。たとえば、重要な業務コンテンツ (弁護士依頼人間の秘匿特権や秘密保持契約書に関わる情報など) を含むアイテムが推奨事項によって検出された際に、ユーザーは保持ラベルを自動適用し、必要に応じてアイテムを機密扱いにして保持することができます。</span><span class="sxs-lookup"><span data-stu-id="cebaf-p102">The Office 365 Security & Compliance Center provides recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they’re classified and retained as needed.</span></span>

<span data-ttu-id="cebaf-110">このトピックでは、ユーザーに表示される可能性があるデータ ガバナンスの推奨事項を一覧表示し、それぞれの推奨事項をトリガーするコンテンツについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cebaf-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="cebaf-111">ボイスメールのクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="cebaf-111">Clean up voicemail</span></span>

<span data-ttu-id="cebaf-p103">この推奨事項は、メッセージの種類が “ボイスメール” と識別されるメール メッセージがユーザーのメールボックスで検出されたときに表示されます。詳細については、「[Exchange でのメッセージのプロパティ](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cebaf-p103">This recommendation appears when email messages identified as the message type ‘voicemail’ are detected in users’ mailboxes. Learn more about [message properties in Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="cebaf-114">弁護士/依頼人特権関連コンテンツのラベル付け</span><span class="sxs-lookup"><span data-stu-id="cebaf-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="cebaf-115">この推奨事項は、次のいずれかの条件が満たされた場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cebaf-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="cebaf-116">メール メッセージの本文で、これらのキーワードのいずれの組み合わせも検出されます。</span><span class="sxs-lookup"><span data-stu-id="cebaf-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="cebaf-117">ACP</span><span class="sxs-lookup"><span data-stu-id="cebaf-117">ACP</span></span>
    - <span data-ttu-id="cebaf-118">弁護士依頼人特権</span><span class="sxs-lookup"><span data-stu-id="cebaf-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="cebaf-119">弁護士/依頼人特権</span><span class="sxs-lookup"><span data-stu-id="cebaf-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="cebaf-120">弁護士/依頼人特権がある</span><span class="sxs-lookup"><span data-stu-id="cebaf-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="cebaf-121">SharePoint ファイルまたは OneDrive ファイルで、これらのキーワードのいずれの組み合わせも検出されます</span><span class="sxs-lookup"><span data-stu-id="cebaf-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="cebaf-122">ACP</span><span class="sxs-lookup"><span data-stu-id="cebaf-122">ACP</span></span>
    - <span data-ttu-id="cebaf-123">弁護士依頼人特権\*</span><span class="sxs-lookup"><span data-stu-id="cebaf-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="cebaf-124">AC 特権</span><span class="sxs-lookup"><span data-stu-id="cebaf-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="cebaf-125">オーディオ ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="cebaf-125">Retain audio files</span></span>

<span data-ttu-id="cebaf-126">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cebaf-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="cebaf-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="cebaf-127">.MP3</span></span>
- <span data-ttu-id="cebaf-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="cebaf-128">.WMA</span></span>
- <span data-ttu-id="cebaf-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="cebaf-129">.WAV</span></span>
- <span data-ttu-id="cebaf-130">.RA</span><span class="sxs-lookup"><span data-stu-id="cebaf-130">.RA</span></span>
- <span data-ttu-id="cebaf-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="cebaf-131">.RAM</span></span>
- <span data-ttu-id="cebaf-132">.RM</span><span class="sxs-lookup"><span data-stu-id="cebaf-132">.RM</span></span>
- <span data-ttu-id="cebaf-133">.MID</span><span class="sxs-lookup"><span data-stu-id="cebaf-133">.MID</span></span>
- <span data-ttu-id="cebaf-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="cebaf-134">.OGG</span></span>
- <span data-ttu-id="cebaf-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="cebaf-135">.AIFF</span></span>
- <span data-ttu-id="cebaf-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="cebaf-136">.PCM</span></span>
- <span data-ttu-id="cebaf-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="cebaf-137">.AAC</span></span>
- <span data-ttu-id="cebaf-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="cebaf-138">.FLAC</span></span>
- <span data-ttu-id="cebaf-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="cebaf-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="cebaf-140">CAD ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="cebaf-140">Retain CAD files</span></span>

<span data-ttu-id="cebaf-141">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cebaf-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="cebaf-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="cebaf-142">.3DXML</span></span>
- <span data-ttu-id="cebaf-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="cebaf-143">.ACIS</span></span>
- <span data-ttu-id="cebaf-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="cebaf-144">.ARC</span></span>
- <span data-ttu-id="cebaf-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="cebaf-145">.ASM</span></span>
- <span data-ttu-id="cebaf-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="cebaf-146">.CAT\*</span></span>
- <span data-ttu-id="cebaf-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="cebaf-147">.CGR</span></span>
- <span data-ttu-id="cebaf-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="cebaf-148">.DW\*</span></span>
- <span data-ttu-id="cebaf-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="cebaf-149">.DX\*</span></span>
- <span data-ttu-id="cebaf-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="cebaf-150">.EDRW</span></span>
- <span data-ttu-id="cebaf-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="cebaf-151">.IAM</span></span>
- <span data-ttu-id="cebaf-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="cebaf-152">.IGES</span></span>
- <span data-ttu-id="cebaf-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="cebaf-153">.IGS</span></span>
- <span data-ttu-id="cebaf-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="cebaf-154">.IPT</span></span>
- <span data-ttu-id="cebaf-155">.JT</span><span class="sxs-lookup"><span data-stu-id="cebaf-155">.JT</span></span>
- <span data-ttu-id="cebaf-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="cebaf-156">.MF1</span></span>
- <span data-ttu-id="cebaf-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="cebaf-157">.NEU</span></span>
- <span data-ttu-id="cebaf-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="cebaf-158">.PAR</span></span>
- <span data-ttu-id="cebaf-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="cebaf-159">.PKG</span></span>
- <span data-ttu-id="cebaf-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="cebaf-160">.PRC</span></span>
- <span data-ttu-id="cebaf-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="cebaf-161">.PRT</span></span>
- <span data-ttu-id="cebaf-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="cebaf-162">.PSM</span></span>
- <span data-ttu-id="cebaf-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="cebaf-163">.PWD</span></span>
- <span data-ttu-id="cebaf-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="cebaf-164">.SLD\*</span></span>
- <span data-ttu-id="cebaf-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="cebaf-165">.STEP</span></span>
- <span data-ttu-id="cebaf-166">.STL</span><span class="sxs-lookup"><span data-stu-id="cebaf-166">.STL</span></span>
- <span data-ttu-id="cebaf-167">.STP</span><span class="sxs-lookup"><span data-stu-id="cebaf-167">.STP</span></span>
- <span data-ttu-id="cebaf-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="cebaf-168">.U3D</span></span>
- <span data-ttu-id="cebaf-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="cebaf-169">.UNV</span></span>
- <span data-ttu-id="cebaf-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="cebaf-170">.VRML</span></span>
- <span data-ttu-id="cebaf-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="cebaf-171">.WRL</span></span>
- <span data-ttu-id="cebaf-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="cebaf-172">.X_\*</span></span>
- <span data-ttu-id="cebaf-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="cebaf-173">.XAS</span></span>
- <span data-ttu-id="cebaf-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="cebaf-174">.XMT\*</span></span>
- <span data-ttu-id="cebaf-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="cebaf-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="cebaf-176">画像ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="cebaf-176">Retain image files</span></span>

<span data-ttu-id="cebaf-177">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cebaf-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="cebaf-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="cebaf-178">.JPEG</span></span>
- <span data-ttu-id="cebaf-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="cebaf-179">.GIF</span></span>
- <span data-ttu-id="cebaf-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="cebaf-180">.TIF\*</span></span>
- <span data-ttu-id="cebaf-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="cebaf-181">.BMP</span></span>
- <span data-ttu-id="cebaf-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="cebaf-182">.PNG</span></span>
- <span data-ttu-id="cebaf-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="cebaf-183">.RAW</span></span>
- <span data-ttu-id="cebaf-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="cebaf-184">.PSD</span></span>
- <span data-ttu-id="cebaf-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="cebaf-185">.PSP</span></span>
- <span data-ttu-id="cebaf-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="cebaf-186">.JPG</span></span>
- <span data-ttu-id="cebaf-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="cebaf-187">.EXIF</span></span>
- <span data-ttu-id="cebaf-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="cebaf-188">.PPM</span></span>
- <span data-ttu-id="cebaf-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="cebaf-189">.PGM</span></span>
- <span data-ttu-id="cebaf-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="cebaf-190">.PBM</span></span>
- <span data-ttu-id="cebaf-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="cebaf-191">.PNM</span></span>
- <span data-ttu-id="cebaf-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="cebaf-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="cebaf-193">NDA 関連コンテンツの保持</span><span class="sxs-lookup"><span data-stu-id="cebaf-193">Retain NDA content</span></span> 

<span data-ttu-id="cebaf-194">この推奨事項は、次のいずれかの条件が満たされた場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cebaf-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="cebaf-195">メール メッセージの本文で、これらのキーワードのいずれの組み合わせも検出されます。</span><span class="sxs-lookup"><span data-stu-id="cebaf-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="cebaf-196">NDA</span><span class="sxs-lookup"><span data-stu-id="cebaf-196">NDA</span></span>
    - <span data-ttu-id="cebaf-197">“秘密保持契約”</span><span class="sxs-lookup"><span data-stu-id="cebaf-197">“Non-Disclosure Agreement”</span></span>
    - <span data-ttu-id="cebaf-198">“秘密保持契約”</span><span class="sxs-lookup"><span data-stu-id="cebaf-198">“Non Disclosure Agreement”</span></span>

- <span data-ttu-id="cebaf-199">SharePoint または OneDrive の .PDF または .DOC ファイルで、これらのキーワードのいずれの組み合わせも検出されます。</span><span class="sxs-lookup"><span data-stu-id="cebaf-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="cebaf-200">NDA</span><span class="sxs-lookup"><span data-stu-id="cebaf-200">NDA</span></span>
    - <span data-ttu-id="cebaf-201">“秘密保持契約”</span><span class="sxs-lookup"><span data-stu-id="cebaf-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="cebaf-202">ソフトウェア開発ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="cebaf-202">Retain software development files</span></span>

<span data-ttu-id="cebaf-203">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cebaf-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="cebaf-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="cebaf-204">.ASAX</span></span>
- <span data-ttu-id="cebaf-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="cebaf-205">.ASM</span></span>
- <span data-ttu-id="cebaf-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="cebaf-206">.ASP\*</span></span>
- <span data-ttu-id="cebaf-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="cebaf-207">.BAT</span></span>
- <span data-ttu-id="cebaf-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="cebaf-208">.CONFIG</span></span>
- <span data-ttu-id="cebaf-209">.CS</span><span class="sxs-lookup"><span data-stu-id="cebaf-209">.CS</span></span>
- <span data-ttu-id="cebaf-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="cebaf-210">.CSS</span></span>
- <span data-ttu-id="cebaf-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="cebaf-211">.DISCO</span></span>
- <span data-ttu-id="cebaf-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="cebaf-212">.HTM\*</span></span>
- <span data-ttu-id="cebaf-213">.INC</span><span class="sxs-lookup"><span data-stu-id="cebaf-213">.INC</span></span>
- <span data-ttu-id="cebaf-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="cebaf-214">.JAD</span></span>
- <span data-ttu-id="cebaf-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="cebaf-215">.JAVA</span></span>
- <span data-ttu-id="cebaf-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="cebaf-216">.JS\*</span></span>
- <span data-ttu-id="cebaf-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="cebaf-217">.LIB</span></span>
- <span data-ttu-id="cebaf-218">.O</span><span class="sxs-lookup"><span data-stu-id="cebaf-218">.O</span></span>
- <span data-ttu-id="cebaf-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="cebaf-219">.PHP</span></span>
- <span data-ttu-id="cebaf-220">.RC</span><span class="sxs-lookup"><span data-stu-id="cebaf-220">.RC</span></span>
- <span data-ttu-id="cebaf-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="cebaf-221">.RESX</span></span>
- <span data-ttu-id="cebaf-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="cebaf-222">.RPT</span></span>
- <span data-ttu-id="cebaf-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="cebaf-223">.RSS</span></span>
- <span data-ttu-id="cebaf-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="cebaf-224">.SCPT</span></span>
- <span data-ttu-id="cebaf-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="cebaf-225">.SRC</span></span>
- <span data-ttu-id="cebaf-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="cebaf-226">.VB\*</span></span>
- <span data-ttu-id="cebaf-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="cebaf-227">.WSF</span></span>
- <span data-ttu-id="cebaf-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="cebaf-228">.XCODEPROJ</span></span>
- <span data-ttu-id="cebaf-229">.XML</span><span class="sxs-lookup"><span data-stu-id="cebaf-229">.XML</span></span>
- <span data-ttu-id="cebaf-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="cebaf-230">.XSD</span></span>
- <span data-ttu-id="cebaf-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="cebaf-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="cebaf-232">ビデオ ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="cebaf-232">Retain video files</span></span>

<span data-ttu-id="cebaf-233">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cebaf-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="cebaf-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="cebaf-234">.AVCHD</span></span>
- <span data-ttu-id="cebaf-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="cebaf-235">.AVI</span></span>
- <span data-ttu-id="cebaf-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="cebaf-236">.FLV</span></span>
- <span data-ttu-id="cebaf-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="cebaf-237">.MOV</span></span>
- <span data-ttu-id="cebaf-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="cebaf-238">.MP2V</span></span>
- <span data-ttu-id="cebaf-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="cebaf-239">.MP4</span></span>
- <span data-ttu-id="cebaf-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="cebaf-240">.MP4V</span></span>
- <span data-ttu-id="cebaf-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="cebaf-241">.MPE</span></span>
- <span data-ttu-id="cebaf-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="cebaf-242">.MPEG</span></span>
- <span data-ttu-id="cebaf-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="cebaf-243">.MPEG1</span></span>
- <span data-ttu-id="cebaf-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="cebaf-244">.MPEG2</span></span>
- <span data-ttu-id="cebaf-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="cebaf-245">.MPEG4</span></span>
- <span data-ttu-id="cebaf-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="cebaf-246">.MPG</span></span>
- <span data-ttu-id="cebaf-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="cebaf-247">.MPG2</span></span>
- <span data-ttu-id="cebaf-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="cebaf-248">.MPG4</span></span>
- <span data-ttu-id="cebaf-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="cebaf-249">.WMV</span></span>
- <span data-ttu-id="cebaf-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="cebaf-250">.XMV</span></span>
