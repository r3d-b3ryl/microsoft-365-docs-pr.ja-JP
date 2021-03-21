---
title: Microsoft 365 のデータ損失防止のオンプレミス スキャナーについての詳細情報 (プレビュー)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 365 データ損失防止のオンプレミス スキャナーは、ファイル　アクティビティの監視とそれらのファイルの保護アクションを、オンプレミスのファイル共有と SharePoint フォルダーおよびドキュメント ライブラリに拡張します。 ファイルは、Azure Information Protection (AIP) スキャナーによってスキャンされ、保護されます
ms.openlocfilehash: fa1c14520c8ad0afa4856fdd8a1c59a0f71f400d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917813"
---
# <a name="learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="06bfb-104">Microsoft 365 のエンドポイントのデータ損失防止について学ぶ (プレビュー) </span><span class="sxs-lookup"><span data-stu-id="06bfb-104">Learn about the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="06bfb-105">Microsoft Data Loss Prevention (オンプレミス スキャナー) は、Microsoft 365 サービス全体で機密アイテムを検出して保護する Microsoft 365 Data Loss Prevention (DLP) スイートの機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="06bfb-105">Microsoft data loss prevention on-premises scanner is part of the Microsoft 365 data loss prevention (DLP) suite of features that you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="06bfb-106">Microsoft のすべての DLP 製品 の詳細については、 「[データ損失防止の概要](data-loss-prevention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06bfb-106">For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="06bfb-107">**DLP オンプレミス スキャナー** は、ファイル共有と SharePoint ドキュメント ライブラリおよびフォルダー内のオンプレミスの保存データをクロールして、漏洩した場合に組織にリスクをもたらしたり、コンプライアンス ポリシー違反のリスクをもたらしたりする機密アイテムを探します。</span><span class="sxs-lookup"><span data-stu-id="06bfb-107">The **DLP on-premises scanner** crawls on-premises data-at-rest in file shares and SharePoint document libraries and folders for sensitive items that, if leaked, would pose a risk to your organization or pose a risk of compliance policy violation.</span></span> <span data-ttu-id="06bfb-108">これにより、機密性の高いアイテムが適切に使用および保護されていることを確認し、危険にさらされる可能性のある動作を防止するために必要な可視性と制御を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="06bfb-108">This gives you the visibility and control you need to ensure that sensitive items are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span> <span data-ttu-id="06bfb-109">DLP オンプレミス スキャナーは、[組み込み](sensitive-information-type-entity-definitions.md)または[カスタムの機密情報](create-a-custom-sensitive-information-type.md)タイプ、[機密ラベル](sensitivity-labels.md)、またはファイル プロパティを使用して機密情報を検出します。</span><span class="sxs-lookup"><span data-stu-id="06bfb-109">The DLP on-premises scanner detects sensitive information by using [built-in](sensitive-information-type-entity-definitions.md) or [custom sensitive information](create-a-custom-sensitive-information-type.md) types, [sensitivity labels](sensitivity-labels.md) or file properties.</span></span> <span data-ttu-id="06bfb-110">機密アイテムを使用してユーザーが行っていることに関する情報が[Activity Explorer](data-classification-activity-explorer.md)に表示され、[DLPポリシー](create-test-tune-dlp-policy.md)を通して、それらのアイテムに保護アクションを適用できます。</span><span class="sxs-lookup"><span data-stu-id="06bfb-110">The information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="the-dlp-on-premises-scanner-relies-on-azure-information-protection-scanner"></a><span data-ttu-id="06bfb-111">DLP オンプレミス スキャナーは Azure Information Protection スキャナーに依存しています</span><span class="sxs-lookup"><span data-stu-id="06bfb-111">The DLP on-premises scanner relies on Azure Information Protection scanner</span></span>

<span data-ttu-id="06bfb-112">DLP オンプレミス スキャナーは、Azure Information Protection (AIP) スキャナーの完全な実装に依存して、機密性の高いアイテムを監視、ラベル付け、保護します。</span><span class="sxs-lookup"><span data-stu-id="06bfb-112">The DLP on-premises scanner relies on a full implementation of the Azure Information Protection (AIP) scanner to monitor, label and protect sensitive items.</span></span> <span data-ttu-id="06bfb-113">AIP スキャナーに慣れていない場合は、AIP スキャナーに慣れておくことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="06bfb-113">If you aren't familiar with the AIP scanner, we strongly recommend familiarizing yourself with it.</span></span> <span data-ttu-id="06bfb-114">次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06bfb-114">See these articles:</span></span>

- [<span data-ttu-id="06bfb-115">Azure Information Protection とは</span><span class="sxs-lookup"><span data-stu-id="06bfb-115">What is Azure Information Protection</span></span>](/azure/information-protection/what-is-information-protection)
- [<span data-ttu-id="06bfb-116">Azure Information Protection 統合ラベル付けスキャナーとは</span><span class="sxs-lookup"><span data-stu-id="06bfb-116">What is the Azure Information Protection unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner)
- [<span data-ttu-id="06bfb-117">Azure Information Protection 統合ラベリング スキャナーをインストールおよび展開するための要件</span><span class="sxs-lookup"><span data-stu-id="06bfb-117">Requirements for installing and deploying the Azure Information Protection unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-prereqs)
- [<span data-ttu-id="06bfb-118">チュートリアル: Azure Information Protection (AIP) 統合ラベル付けスキャナーのインストール</span><span class="sxs-lookup"><span data-stu-id="06bfb-118">Tutorial: Installing the Azure Information Protection (AIP) unified labeling scanner</span></span>](/azure/information-protection/tutorial-install-scanner)
- [<span data-ttu-id="06bfb-119">Azure Information Protection 統合ラベル付けスキャナーの構成とインストール</span><span class="sxs-lookup"><span data-stu-id="06bfb-119">Configuring and installing the Azure Information Protection unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install)
- [<span data-ttu-id="06bfb-120">Azure Information Protection 統合されたラベル付けクライアント - バージョンのリリース履歴とサポート ポリシー</span><span class="sxs-lookup"><span data-stu-id="06bfb-120">Azure Information Protection unified labeling client - Version release history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)

## <a name="dlp-on-premises-scanner-actions"></a><span data-ttu-id="06bfb-121">DLP オンプレミス スキャナーのアクション</span><span class="sxs-lookup"><span data-stu-id="06bfb-121">DLP on-premises scanner actions</span></span>

<span data-ttu-id="06bfb-122">DLP オンプレミス スキャナーは、次の 4 つの方法のいずれかを使用してファイルを検出します。</span><span class="sxs-lookup"><span data-stu-id="06bfb-122">DLP on-premises scanner detects files by one of these four methods:</span></span>

- <span data-ttu-id="06bfb-123">機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="06bfb-123">sensitive information types</span></span>
- <span data-ttu-id="06bfb-124">機密度ラベル</span><span class="sxs-lookup"><span data-stu-id="06bfb-124">sensitivity labels</span></span>
- <span data-ttu-id="06bfb-125">ファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="06bfb-125">file extension</span></span>
- <span data-ttu-id="06bfb-126">Office ファイルのみのカスタム ドキュメント プロパティ</span><span class="sxs-lookup"><span data-stu-id="06bfb-126">custom document properties on Office files only</span></span> 

<span data-ttu-id="06bfb-127">検出されたファイルがリークまたはコンプライアンス ポリシー違反の場合に潜在的なリスクをもたらす場合、DLP オンプレミス スキャナーはこれらの4つのアクションのいずれかを実行できます。</span><span class="sxs-lookup"><span data-stu-id="06bfb-127">When a detected file poses a potential risk if leaked or a compliance policy violation, the DLP on-premises scanner can take one of these four actions.</span></span>

|<span data-ttu-id="06bfb-128">アクション</span><span class="sxs-lookup"><span data-stu-id="06bfb-128">Action</span></span> |<span data-ttu-id="06bfb-129">説明</span><span class="sxs-lookup"><span data-stu-id="06bfb-129">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="06bfb-130">**これらの人々がオンプレミス スキャナーに保存されているファイルにアクセスするのをブロックします - 全員**</span><span class="sxs-lookup"><span data-stu-id="06bfb-130">**Block these people from accessing file stored in  on-premises scanner - Everyone**</span></span> | <span data-ttu-id="06bfb-131">適用されると、このアクションは、コンテンツ所有者、アイテムを変更した最後のアカウント、および管理者を除くすべてのアカウントへのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="06bfb-131">When enforced, this action blocks access to all accounts except the content owner, the last account that modified the item and the administrator.</span></span> <span data-ttu-id="06bfb-132">これは、ファイル所有者、リポジトリ所有者 ([[コンテンツ スキャン ジョブのリポジトリ所有者設定の設定]](/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview) で設定)、最後の修飾子 (SharePoint でのみ識別可能)、および管理者を除く、ファイルレベルで NTFS/SharePoint アクセス許可からすべてのアカウントを削除することによって行われます。 スキャナー アカウントには、ファイルに対する FC 権限も付与されます。</span><span class="sxs-lookup"><span data-stu-id="06bfb-132">It does this by removing all accounts from NTFS/SharePoint permissions at the file level except the file owner, repository owner (set in the [Set repository owner](/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview) setting in content scan job), last modifier (can be identified in SharePoint only) and admin. The scanner account is also granted FC rights on the file.</span></span>|
|<span data-ttu-id="06bfb-133">**これらの人々がオンプレミス スキャナーに保存されているファイルにアクセスするのをブロックします - 組織全体の (パブリック) アクセスをブロック**</span><span class="sxs-lookup"><span data-stu-id="06bfb-133">**Block these people from accessing file stored in  on-premises scanner - block org-wide (public) access**</span></span>    |<span data-ttu-id="06bfb-134">このアクションを実行すると、**_Everyone_*_、_*_NT AUTHORITY\authentication users_*_、および_*_Domain Users_** SIDがファイルアクセス制御リスト (ACL) から削除されます。</span><span class="sxs-lookup"><span data-stu-id="06bfb-134">When enforced, this action removes the **_Everyone_*_, _*_NT AUTHORITY\authenticated users_*_, and _*_Domain Users_** SIDs from the file access control list (ACL).</span></span> <span data-ttu-id="06bfb-135">ファイルまたは親フォルダへの権限が明示的に付与されているユーザーとグループのみがファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="06bfb-135">Only users and groups that have been explicitly granted rights to the file or parent folder will be able to access the file.</span></span>|
|<span data-ttu-id="06bfb-136">**ファイルに権限を設定する**</span><span class="sxs-lookup"><span data-stu-id="06bfb-136">**Set permissions on the file**</span></span>|<span data-ttu-id="06bfb-137">適用されると、このアクションはファイルにその親フォルダーのアクセス許可を継承させます。</span><span class="sxs-lookup"><span data-stu-id="06bfb-137">When enforced, this action forces the file to inherit the permissions of its parent folder.</span></span> <span data-ttu-id="06bfb-138">デフォルトでは、このアクションは、親フォルダーのアクセス許可が、ファイルに既に存在するアクセス許可よりも制限されている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="06bfb-138">Be default, this action will only be enforced if the permissions on the parent folder are more restrictive than the permissions that are already on the file.</span></span> <span data-ttu-id="06bfb-139">たとえば、ファイルの ACL が \**_特定のユーザー_*_のみを許可するように設定されており、親フォルダーが_*_Domain Users_*_グループを許可するように構成されている場合、親フォルダーのアクセス許可はファイルに継承されません。\* 親のアクセス許可の制限が緩い場合でも、[継承]を選択すると、この動作を上書きできます\*\*。</span><span class="sxs-lookup"><span data-stu-id="06bfb-139">For example, if the ACL on the file is set to only allow **_specific users_*_ and the parent folder is configured to allow _*_Domain Users_*_ group, the parent folder permissions would not be inherited by the file. You can override this behavior by selecting the _\* Inherit even if parent permissions are less restrictive*\* option.</span></span>|
|<span data-ttu-id="06bfb-140">**不適切な場所からファイルを削除する**</span><span class="sxs-lookup"><span data-stu-id="06bfb-140">**Remove the file from improper location**</span></span>|<span data-ttu-id="06bfb-141">強制されると、このアクションは元のファイルを .txt 拡張子の付いたスタブ ファイルに置き換え、元のファイルのコピーを検疫フォルダーに配置します。</span><span class="sxs-lookup"><span data-stu-id="06bfb-141">When enforced, this action replaces the original file with a stub file with .txt extension and places a copy of the original file in a quarantine folder.</span></span> 

## <a name="whats-different-in-the-on-premises-scanner"></a><span data-ttu-id="06bfb-142">オンプレミス スキャナーの違い</span><span class="sxs-lookup"><span data-stu-id="06bfb-142">What's different in the on-premises scanner</span></span>

<span data-ttu-id="06bfb-143">オンプレミス スキャナーを掘り下げる前に知っておく必要のあるいくつかの追加の概念があります。</span><span class="sxs-lookup"><span data-stu-id="06bfb-143">There are a few extra concepts that you need to be aware of before you dig into the on-premises scanner.</span></span>

### <a name="aip-repositories-and-content-scan-jobs"></a><span data-ttu-id="06bfb-144">AIP リポジトリとコンテンツ スキャン ジョブ</span><span class="sxs-lookup"><span data-stu-id="06bfb-144">AIP repositories and content scan jobs</span></span>

<span data-ttu-id="06bfb-145">AIP コンテンツ スキャン ジョブを作成し、DLP エンジンで評価するファイルをホストするリポジトリを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06bfb-145">You must create an AIP content scan jobs and identify the repositories that host the files that you want to be evaluated by DLP engine.</span></span> <span data-ttu-id="06bfb-146">作成した AIP コンテンツ スキャン ジョブで DLP ルールが有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="06bfb-146">Make sure you enable DLP rules in the created AIP content scan job.</span></span>

### <a name="policy-tips"></a><span data-ttu-id="06bfb-147">ポリシー ヒント</span><span class="sxs-lookup"><span data-stu-id="06bfb-147">Policy tips</span></span>

<span data-ttu-id="06bfb-148">[ポリシー ヒント](use-notifications-and-policy-tips.md)は、オンプレミス スキャナーでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="06bfb-148">[Policy tips](use-notifications-and-policy-tips.md) are not available in on-premises scanner.</span></span>


### <a name="viewing-dlp-on-premises-scanner-events"></a><span data-ttu-id="06bfb-149">DLP オンプレミス スキャナー イベントの表示</span><span class="sxs-lookup"><span data-stu-id="06bfb-149">Viewing DLP on-premises scanner events</span></span>

<span data-ttu-id="06bfb-150">DLP オンプレミス スキャナー データは、M365 コンプライアンス センター [アクティビティ エクスプローラー](data-classification-activity-explorer.md)で表示します。</span><span class="sxs-lookup"><span data-stu-id="06bfb-150">You view DLP on-premises scanner data in the M365 Compliance Center [activity explorer](data-classification-activity-explorer.md).</span></span> 

## <a name="next-steps"></a><span data-ttu-id="06bfb-151">次のステップ</span><span class="sxs-lookup"><span data-stu-id="06bfb-151">Next steps</span></span>

<span data-ttu-id="06bfb-152">ここまで DLP オンプレミス スキャナーについて学びましたので、次のステップは以下になります:</span><span class="sxs-lookup"><span data-stu-id="06bfb-152">Now that you've learned about DLP on-premises scanner, your next steps are:</span></span>

1. [<span data-ttu-id="06bfb-153">DLP オンプレミス スキャナーの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="06bfb-153">Get started with the DLP on-premises scanner</span></span>](dlp-on-premises-scanner-get-started.md)
2. [<span data-ttu-id="06bfb-154">DLP オンプレミス スキャナーを使用する</span><span class="sxs-lookup"><span data-stu-id="06bfb-154">Use the DLP on-premises scanner</span></span>](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a><span data-ttu-id="06bfb-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="06bfb-155">See also</span></span>

- [<span data-ttu-id="06bfb-156">Getting started with the Microsoft data loss prevention on-premises scanner (Microsoft データ損失防止オンプレミス スキャナーの使用を開始する)</span><span class="sxs-lookup"><span data-stu-id="06bfb-156">Getting started with the Microsoft data loss prevention on-premises scanner</span></span>](dlp-on-premises-scanner-get-started.md)
- [<span data-ttu-id="06bfb-157">Use the Microsoft data loss prevention on-premises scanner (Microsoft データ損失防止オンプレミス スキャナーを使用する)</span><span class="sxs-lookup"><span data-stu-id="06bfb-157">Use the Microsoft data loss prevention on-premises scanner</span></span>](dlp-on-premises-scanner-use.md)
- [<span data-ttu-id="06bfb-158">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="06bfb-158">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="06bfb-159">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="06bfb-159">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="06bfb-160">Activity Explorer を使い始める</span><span class="sxs-lookup"><span data-stu-id="06bfb-160">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)