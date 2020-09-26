---
title: 二重キー暗号化の概要とよくある FAQ
description: Microsoft 365 の二重キー暗号化についてよく寄せられる質問。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 09/22/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 98c61e66155e21624e8ecba460ebc3041e72ada5
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277656"
---
# <a name="double-key-encryption-frequently-asked-questions"></a><span data-ttu-id="22ef0-103">二重キー暗号化についてよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="22ef0-103">Double Key Encryption frequently asked questions</span></span>

<span data-ttu-id="22ef0-104">二重キー暗号化のしくみについての質問がありますか。</span><span class="sxs-lookup"><span data-stu-id="22ef0-104">Have a question about how Double Key Encryption works?</span></span> <span data-ttu-id="22ef0-105">ここで回答を確認してください。</span><span class="sxs-lookup"><span data-stu-id="22ef0-105">Check for an answer here.</span></span>

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a><span data-ttu-id="22ef0-106">Microsoft 365 (DKE) の二重キー暗号化とは</span><span class="sxs-lookup"><span data-stu-id="22ef0-106">What is Double Key Encryption for Microsoft 365 (DKE)?</span></span>

<span data-ttu-id="22ef0-107">Microsoft 365 の二重キー暗号化により、お客様は、特殊な要件を満たすように機密性の高いデータを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="22ef0-107">Double Key Encryption for Microsoft 365 enables customers to protect their highly sensitive data to meet specialized requirements.</span></span> <span data-ttu-id="22ef0-108">お客様は、暗号化キーのフルコントロールを維持することができます。</span><span class="sxs-lookup"><span data-stu-id="22ef0-108">It helps customers maintain full control of their encryption keys.</span></span> <span data-ttu-id="22ef0-109">2つのキーを使用してデータを保護します。コントロール内の1つのキーと、Microsoft Azure に安全に格納されている2番目のキー。</span><span class="sxs-lookup"><span data-stu-id="22ef0-109">It uses two keys to protect data; one key in your control and a second key stored securely in Microsoft Azure.</span></span> <span data-ttu-id="22ef0-110">2つのキー暗号化で保護されたデータを表示するには、両方のキーにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="22ef0-110">Viewing data protected with Double Key Encryption requires access to both keys.</span></span> <span data-ttu-id="22ef0-111">Microsoft は、これらのキーのいずれか1つにしかアクセスできないため、保護されたデータは Microsoft からはアクセスできないままになり、データのプライバシーとセキュリティを完全に制御できるようになります。</span><span class="sxs-lookup"><span data-stu-id="22ef0-111">Since Microsoft can access only one of these keys, protected data remains inaccessible to Microsoft, ensuring that you have full control over your data privacy and security.</span></span>  

<span data-ttu-id="22ef0-112">キーの要求に使用する Double キー暗号化サービスは、任意の場所 (オンプレミスのキー管理サーバーまたはクラウド) にホストできます。</span><span class="sxs-lookup"><span data-stu-id="22ef0-112">You can host the Double Key Encryption service used to request your key, in a location of your choice (on-premises key management server or in the cloud).</span></span> <span data-ttu-id="22ef0-113">他のアプリケーションと同様にサービスを維持します。</span><span class="sxs-lookup"><span data-stu-id="22ef0-113">You maintain the service as you would any other application.</span></span> <span data-ttu-id="22ef0-114">二重キー暗号化を使用すると、二重キー暗号化サービスへのアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="22ef0-114">Double Key Encryption enables you to control access to the Double Key Encryption service.</span></span> <span data-ttu-id="22ef0-115">非常に機密性の高いデータを社内に保存したり、クラウドに移動したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="22ef0-115">You can store your highly sensitive data on-premises or move it to the cloud.</span></span> <span data-ttu-id="22ef0-116">キーのフルコントロールを維持しているため、サードパーティからのアクセスを禁止することができます。</span><span class="sxs-lookup"><span data-stu-id="22ef0-116">You can be confident about preventing third-party access because you maintain full control of your key.</span></span> <span data-ttu-id="22ef0-117">[Double キー暗号化] を使用すると、データとキーを同じ場所に格納できます。</span><span class="sxs-lookup"><span data-stu-id="22ef0-117">Double Key Encryption allows you to store your data and key in the same location.</span></span>

<span data-ttu-id="22ef0-118">DKE は、一般的なデータ保護規則 (GDPR)、医療保険の携行性と責任に関する法律 (HIPAA)、グラムリーチブライ Act (GLBA)、ロシアのデータローカリゼーション法律 (連邦法) など、いくつかの規制および基準における規制要件を満たすのに役立つ情報を示します。</span><span class="sxs-lookup"><span data-stu-id="22ef0-118">DKE helps you meet regulatory requirements across several regulations and standards such as the General Data Protection Regulation (GDPR), the Health Insurance Portability and Accountability Act (HIPAA), the Gramm-Leach-Bliley Act (GLBA), Russia’s data localization law – Federal Law No.</span></span> <span data-ttu-id="22ef0-119">242-FZ、オーストラリアの連邦プライバシー法1988、ニュージーランドのプライバシー法1993。</span><span class="sxs-lookup"><span data-stu-id="22ef0-119">242-FZ, Australia’s Federal Privacy Act 1988, and New Zealand’s Privacy Act 1993.</span></span>

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a><span data-ttu-id="22ef0-120">Microsoft Office の組み込みの機密ラベルで、二重のキー暗号化を使用することはできますか?</span><span class="sxs-lookup"><span data-stu-id="22ef0-120">Can I use Double Key Encryption with Microsoft Office built-in sensitivity labeling?</span></span>

<span data-ttu-id="22ef0-121">Azure Information Protection ユニファイドラベルクライアントを使用して、2重のキー暗号化でドキュメントを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22ef0-121">You'll need to use the Azure Information Protection unified labeling client to protect documents with Double Key Encryption.</span></span> <span data-ttu-id="22ef0-122">現時点では、Microsoft Office の組み込みの機密ラベルを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="22ef0-122">Currently, you can't use Microsoft Office built-in sensitivity labeling.</span></span> 

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a><span data-ttu-id="22ef0-123">DKE ではどのような Microsoft 365 アプリを使用できますか?</span><span class="sxs-lookup"><span data-stu-id="22ef0-123">What Microsoft 365 Apps can I use with DKE?</span></span>

<span data-ttu-id="22ef0-124">DKE ラベルを使用すると、Windows のデスクトップ版の Word、Excel、および PowerPoint を使用してドキュメントを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="22ef0-124">You can use DKE labels to protect documents using the desktop versions of Word, Excel, and PowerPoint on Windows.</span></span> <span data-ttu-id="22ef0-125">Windows で \* 12711 以降 (デスクトップ版の Word、PowerPoint、Excel) を使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="22ef0-125">Ensure that you're using \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a><span data-ttu-id="22ef0-126">既存のキー (HYOK) ソリューションとは異なる二重キー暗号化と既存のキーの違い</span><span class="sxs-lookup"><span data-stu-id="22ef0-126">How is Double Key Encryption different from the existing hold your own key (HYOK) solution?</span></span>

<span data-ttu-id="22ef0-127">二重キー暗号化は、2つのキーでデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="22ef0-127">Double Key Encryption encrypts your data with two keys.</span></span> <span data-ttu-id="22ef0-128">暗号化キーはコントロール内にあり、2番目のキーは Microsoft Azure に格納されているため、暗号化されたデータをクラウドに移行できます。</span><span class="sxs-lookup"><span data-stu-id="22ef0-128">Your encryption key is in your control and the second key is stored in Microsoft Azure, allowing you to move your encrypted data to the cloud.</span></span> <span data-ttu-id="22ef0-129">HYOK は、1つのキーでコンテンツを保護し、キーは常にオンプレミスで保護されます。</span><span class="sxs-lookup"><span data-stu-id="22ef0-129">HYOK protects your content with only one key and the key is always on premises.</span></span>  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a><span data-ttu-id="22ef0-130">二重の重要な暗号化ドキュメントは外部で共有できますか?</span><span class="sxs-lookup"><span data-stu-id="22ef0-130">Can Double Key Encrypted documents be shared externally?</span></span>

<span data-ttu-id="22ef0-131">2つの暗号化されたドキュメントを、ユーザーとは別のテナントのユーザーと共有することができます。</span><span class="sxs-lookup"><span data-stu-id="22ef0-131">You can share Double Key Encrypted documents with users on a separate tenant as long as those users:</span></span>

- <span data-ttu-id="22ef0-132">二重キー暗号化サービスのキーにアクセスするために必要なアクセス許可があること。</span><span class="sxs-lookup"><span data-stu-id="22ef0-132">Have the required permission to access your key in your Double Key Encryption service.</span></span>

- <span data-ttu-id="22ef0-133">Microsoft Azure のキーにアクセスするために必要なアクセス許可が付与されている。</span><span class="sxs-lookup"><span data-stu-id="22ef0-133">Have the required permission to access your key in Microsoft Azure.</span></span>

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a><span data-ttu-id="22ef0-134">HYOK で保護されているドキュメントの処理</span><span class="sxs-lookup"><span data-stu-id="22ef0-134">What happens to documents that are protected with HYOK?</span></span>

<span data-ttu-id="22ef0-135">二重キー暗号化の展開は、既存の HYOK セットアップには影響しません。</span><span class="sxs-lookup"><span data-stu-id="22ef0-135">Deploying Double Key Encryption won't affect your existing HYOK setup.</span></span> <span data-ttu-id="22ef0-136">ただし、HYOK と並行して二重キー暗号化の使用を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="22ef0-136">However, we recommend that you start using Double Key Encryption in parallel with HYOK.</span></span>

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a><span data-ttu-id="22ef0-137">Microsoft 以外の gapped 環境で、二重のキー暗号化を実行できますか。</span><span class="sxs-lookup"><span data-stu-id="22ef0-137">Can I run Double Key Encryption in my non-Microsoft air-gapped environment?</span></span>

<span data-ttu-id="22ef0-138">DKE は、Microsoft Azure へのアクセスを必要とするため、これらの環境をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="22ef0-138">DKE doesn't support these environments because the service requires access to Microsoft Azure.</span></span>

## <a name="where-can-i-store-double-key-encrypted-documents"></a><span data-ttu-id="22ef0-139">二重キーで暗号化されたドキュメントはどこに保存できますか?</span><span class="sxs-lookup"><span data-stu-id="22ef0-139">Where can I store Double Key Encrypted documents?</span></span>

<span data-ttu-id="22ef0-140">二重キーで暗号化されたドキュメントを社内またはクラウドに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="22ef0-140">You can store Double Key Encrypted documents on-premises or in the cloud.</span></span> <span data-ttu-id="22ef0-141">クラウドでは、暗号化されたコンテンツを SharePoint Online と OneDrive for business に移動できます。</span><span class="sxs-lookup"><span data-stu-id="22ef0-141">In the cloud, you can move encrypted content to SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="22ef0-142">Microsoft は秘密キーへのアクセス権を持っていないため、暗号化されたデータは Microsoft に対して非透過の状態になります。</span><span class="sxs-lookup"><span data-stu-id="22ef0-142">Since Microsoft doesn't have access to your private key, the encrypted data remains opaque to Microsoft.</span></span> <span data-ttu-id="22ef0-143">これは、Office Web Apps で暗号化されたドキュメントをオンラインで表示できないことも意味します。</span><span class="sxs-lookup"><span data-stu-id="22ef0-143">This also means that you can't view the encrypted documents online in Office Web Apps.</span></span>

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a><span data-ttu-id="22ef0-144">二重キー暗号化が使用可能な地域と言語</span><span class="sxs-lookup"><span data-stu-id="22ef0-144">What regions and languages is Double Key Encryption available in?</span></span> <span data-ttu-id="22ef0-145">世界中で2重のキー暗号化を利用できますか?</span><span class="sxs-lookup"><span data-stu-id="22ef0-145">Is Double Key Encryption available worldwide?</span></span>

<span data-ttu-id="22ef0-146">DKE ラベルは、Microsoft Information Protection の他の機密ラベルと同じ言語にローカライズされます。</span><span class="sxs-lookup"><span data-stu-id="22ef0-146">DKE labels are localized to the same languages as other sensitivity labels in Microsoft Information Protection.</span></span> <span data-ttu-id="22ef0-147">世界中で使用できる二重キー暗号化があります。</span><span class="sxs-lookup"><span data-stu-id="22ef0-147">Double Key Encryption is available worldwide.</span></span>

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a><span data-ttu-id="22ef0-148">非 DKE ラベルを DKE ラベルに変換することはできますか。</span><span class="sxs-lookup"><span data-stu-id="22ef0-148">Can I convert a non-DKE label to a DKE label?</span></span>

<span data-ttu-id="22ef0-149">いいえ。</span><span class="sxs-lookup"><span data-stu-id="22ef0-149">No.</span></span> <span data-ttu-id="22ef0-150">作成後に DKE をラベルに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="22ef0-150">You can’t add DKE to a label after you create it.</span></span> <span data-ttu-id="22ef0-151">代わりに、[キーの **暗号化を使用** する] を選択し、ラベルの作成時に二重キー暗号化サービスの URL を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22ef0-151">Instead, you must choose **Use Double Key Encryption** and provide the URL of your Double Key Encryption service when you create the label.</span></span>

## <a name="how-do-i-roll-my-dke-keys"></a><span data-ttu-id="22ef0-152">DKE キーをロールするにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="22ef0-152">How do I roll my DKE keys?</span></span>

<span data-ttu-id="22ef0-153">Azure に格納するロール (循環またはキー更新とも呼ばれます) の手順については、「 [Azure Information Protection のテナントキーの操作](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22ef0-153">For instructions on rolling (also called rotating or rekeying) the key you store in Azure, see [Operations for your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key).</span></span>

<span data-ttu-id="22ef0-154">DKE サービスの新しいキーを作成する方法については、「 [テナントとキーの設定](double-key-encryption.md#tenant-and-key-settings) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22ef0-154">See [Tenant and key settings](double-key-encryption.md#tenant-and-key-settings) for information on creating a new key for the DKE service.</span></span>

<span data-ttu-id="22ef0-155">キーを作成するときに、名前と GUID を設定します。</span><span class="sxs-lookup"><span data-stu-id="22ef0-155">When you create a key, you set up a name and a GUID.</span></span> <span data-ttu-id="22ef0-156">キーを回転させると、名前と GUID を持つ古いレコードが保持されますが、同じ名前で GUID が異なる新しいレコードが追加されます。</span><span class="sxs-lookup"><span data-stu-id="22ef0-156">Then, if you rotate a key, you keep the old record with the name and GUID but add a new record with the same name but different GUID.</span></span> <span data-ttu-id="22ef0-157">新しいキーがアクティブとして設定され、公開キー API が新しい暗号化に対してそのキーを返し始めます。</span><span class="sxs-lookup"><span data-stu-id="22ef0-157">The new key gets set as active so that the public key API starts returning it for new encryption.</span></span> <span data-ttu-id="22ef0-158">両方のキーを復号化に使用して、新しいコンテンツと古いコンテンツを復号化できるようにします。</span><span class="sxs-lookup"><span data-stu-id="22ef0-158">Both keys are available for decryption so that new content and old content can be decrypted.</span></span>
