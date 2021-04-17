---
title: データ損失防止ポリシー ヒントリファレンス
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: データ損失防止 (DLP) ポリシーにポリシー ヒントを追加する方法について、DLP ポリシーと競合するコンテンツを操作しているユーザーに通知する方法について学習します。
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 693f511b6303fb07d393c62efb4a61631b844474
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876808"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="5f48c-103">データ損失防止ポリシー ヒントリファレンス</span><span class="sxs-lookup"><span data-stu-id="5f48c-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="5f48c-104">Outlook Web Access の DLP ポリシー ヒントは、以下を除き、DLP ポリシー内の Exchange ワークロードに適用可能なすべての条件、例外、およびアクションでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5f48c-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="5f48c-105">**条件:**</span><span class="sxs-lookup"><span data-stu-id="5f48c-105">**Conditions:**</span></span>

- <span data-ttu-id="5f48c-106">Sender Is</span><span class="sxs-lookup"><span data-stu-id="5f48c-106">Sender Is</span></span>
- <span data-ttu-id="5f48c-107">Sender Domain Is</span><span class="sxs-lookup"><span data-stu-id="5f48c-107">Sender Domain Is</span></span>
- <span data-ttu-id="5f48c-108">受信者は、</span><span class="sxs-lookup"><span data-stu-id="5f48c-108">Recipient is a member of</span></span>
- <span data-ttu-id="5f48c-109">ヘッダーには、単語または語句が含まれています</span><span class="sxs-lookup"><span data-stu-id="5f48c-109">Header contains words or phrases</span></span>
- <span data-ttu-id="5f48c-110">ヘッダーがパターンと一致する</span><span class="sxs-lookup"><span data-stu-id="5f48c-110">Header matches patterns</span></span>
- <span data-ttu-id="5f48c-111">ドキュメント のサイズが等しいか、またはより大きい</span><span class="sxs-lookup"><span data-stu-id="5f48c-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="5f48c-112">メッセージの種類は次の値です。</span><span class="sxs-lookup"><span data-stu-id="5f48c-112">Message type is</span></span>
- <span data-ttu-id="5f48c-113">メッセージの重要度は、</span><span class="sxs-lookup"><span data-stu-id="5f48c-113">Message importance is</span></span>
- <span data-ttu-id="5f48c-114">コンテンツ文字セットに単語が含まれている</span><span class="sxs-lookup"><span data-stu-id="5f48c-114">Content character set contains words</span></span>
- <span data-ttu-id="5f48c-115">件名または本文に単語または語句が含まれる</span><span class="sxs-lookup"><span data-stu-id="5f48c-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="5f48c-116">件名または本文がパターンと一致する</span><span class="sxs-lookup"><span data-stu-id="5f48c-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="5f48c-117">コンテンツ文字セットに単語が含まれている</span><span class="sxs-lookup"><span data-stu-id="5f48c-117">Content character set contains words</span></span>
- <span data-ttu-id="5f48c-118">コンテンツの受信</span><span class="sxs-lookup"><span data-stu-id="5f48c-118">Content is received from</span></span>
- <span data-ttu-id="5f48c-119">送信者がポリシー ヒントを上書きしました</span><span class="sxs-lookup"><span data-stu-id="5f48c-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="5f48c-120">メッセージ サイズが等しいか、またはより大きい</span><span class="sxs-lookup"><span data-stu-id="5f48c-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="5f48c-121">Sender AD属性に単語または語句が含まれている</span><span class="sxs-lookup"><span data-stu-id="5f48c-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="5f48c-122">Sender AD属性がパターンと一致する</span><span class="sxs-lookup"><span data-stu-id="5f48c-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="5f48c-123">ドキュメントコンテンツには、単語または語句が含まれる</span><span class="sxs-lookup"><span data-stu-id="5f48c-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="5f48c-124">ドキュメント コンテンツがパターンと一致する</span><span class="sxs-lookup"><span data-stu-id="5f48c-124">Document content matches patterns</span></span>

<span data-ttu-id="5f48c-125">**アクション:**</span><span class="sxs-lookup"><span data-stu-id="5f48c-125">**Actions:**</span></span>

- <span data-ttu-id="5f48c-126">承認のためにメッセージを送信者のマネージャーに転送する</span><span class="sxs-lookup"><span data-stu-id="5f48c-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="5f48c-127">承認のメッセージを特定の承認者に転送する</span><span class="sxs-lookup"><span data-stu-id="5f48c-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="5f48c-128">メッセージを特定のユーザーにリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="5f48c-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="5f48c-129">宛先ボックスに受信者を追加する</span><span class="sxs-lookup"><span data-stu-id="5f48c-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="5f48c-130">Cc ボックスに受信者を追加する</span><span class="sxs-lookup"><span data-stu-id="5f48c-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="5f48c-131">Bcc ボックスに受信者を追加する</span><span class="sxs-lookup"><span data-stu-id="5f48c-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="5f48c-132">送信者のマネージャーを受信者として追加する</span><span class="sxs-lookup"><span data-stu-id="5f48c-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="5f48c-133">HTML 免責事項の追加</span><span class="sxs-lookup"><span data-stu-id="5f48c-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="5f48c-134">電子メールの件名の先頭に追加する</span><span class="sxs-lookup"><span data-stu-id="5f48c-134">Prepend email subject</span></span>
- <span data-ttu-id="5f48c-135">O365 メッセージの暗号化と権限の保護を削除する</span><span class="sxs-lookup"><span data-stu-id="5f48c-135">Remove O365 Message Encryption and rights protection</span></span>
- <span data-ttu-id="5f48c-136">削除</span><span class="sxs-lookup"><span data-stu-id="5f48c-136">Remove</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="5f48c-137">Outlook 2013 以降では、一部の条件と例外に関するポリシー ヒントの表示がサポートされています</span><span class="sxs-lookup"><span data-stu-id="5f48c-137">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="5f48c-138">現在、Outlook 2013 以降では、以下の条件と対応する例外以外の条件や例外を含むポリシーに関するポリシー ヒントの表示がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5f48c-138">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="5f48c-139">コンテンツが含まれる (機密情報の種類に対してのみ機能します)。</span><span class="sxs-lookup"><span data-stu-id="5f48c-139">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="5f48c-140">感度ラベルはサポートされていません)</span><span class="sxs-lookup"><span data-stu-id="5f48c-140">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="5f48c-141">コンテンツが共有されている</span><span class="sxs-lookup"><span data-stu-id="5f48c-141">Content is shared</span></span>

<span data-ttu-id="5f48c-142">Outlook クライアント アプリで作成された電子メールでは、コンテンツと一致し、コンテンツに対して保護アクションを適用する場合、すべての条件が機能します。</span><span class="sxs-lookup"><span data-stu-id="5f48c-142">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="5f48c-143">ただし、ユーザーにポリシー ヒントを表示する方法は、上記の条件とは別に使用される条件に対してまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5f48c-143">However, showing policy tips to users is not yet supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="5f48c-144">Outlook 2013 以降では、一部の機密情報の種類に関するポリシー ヒントの表示がサポートされています</span><span class="sxs-lookup"><span data-stu-id="5f48c-144">Outlook 2013 and later supports showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="5f48c-145">Outlook on Desktop (2013 以降) で DLP ポリシー ヒントを表示するために検出される、既定の機密情報の種類の一覧は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5f48c-145">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) are the following :</span></span>

- <span data-ttu-id="5f48c-146">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-146">ABA Routing Number</span></span>
- <span data-ttu-id="5f48c-147">アルゼンチンの国民識別 (DNI) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-147">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="5f48c-148">オーストラリアの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-148">Australia Bank Account Number</span></span>
- <span data-ttu-id="5f48c-149">オーストラリアの医療口座番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-149">Australia Medical Account Number</span></span>
- <span data-ttu-id="5f48c-150">オーストラリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-150">Australia Passport Number</span></span>
- <span data-ttu-id="5f48c-151">オーストラリアの納税者番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-151">Australia Tax File Number</span></span>
- <span data-ttu-id="5f48c-152">Azure DocumentDB Auth Key</span><span class="sxs-lookup"><span data-stu-id="5f48c-152">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="5f48c-153">Azure IAAS データベース接続文字列と Azure SQL接続文字列</span><span class="sxs-lookup"><span data-stu-id="5f48c-153">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="5f48c-154">Azure IoT 接続文字列</span><span class="sxs-lookup"><span data-stu-id="5f48c-154">Azure IoT Connection String</span></span>  
- <span data-ttu-id="5f48c-155">Azure 発行設定パスワード</span><span class="sxs-lookup"><span data-stu-id="5f48c-155">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="5f48c-156">Azure Redis キャッシュ接続文字列</span><span class="sxs-lookup"><span data-stu-id="5f48c-156">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="5f48c-157">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="5f48c-157">Azure SAS</span></span>  
- <span data-ttu-id="5f48c-158">Azure Service Bus 接続文字列</span><span class="sxs-lookup"><span data-stu-id="5f48c-158">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="5f48c-159">Azure ストレージ アカウント キー</span><span class="sxs-lookup"><span data-stu-id="5f48c-159">Azure Storage Account Key</span></span>  
- <span data-ttu-id="5f48c-160">Azure ストレージ アカウント キー (汎用)</span><span class="sxs-lookup"><span data-stu-id="5f48c-160">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="5f48c-161">ベルギーの国民番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-161">Belgium National Number</span></span>
- <span data-ttu-id="5f48c-162">ブラジルの CPF 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-162">Brazil CPF Number</span></span>
- <span data-ttu-id="5f48c-163">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="5f48c-163">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="5f48c-164">	ブラジルの国民識別カード (RG)</span><span class="sxs-lookup"><span data-stu-id="5f48c-164">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="5f48c-165">カナダの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-165">Canada Bank Account Number</span></span>
- <span data-ttu-id="5f48c-166">カナダの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-166">Canada Driver's License Number</span></span>
- <span data-ttu-id="5f48c-167">カナダの健康保険番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-167">Canada Health Service Number</span></span>
- <span data-ttu-id="5f48c-168">カナダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-168">Canada Passport Number</span></span>
- <span data-ttu-id="5f48c-169">カナダの個人保健識別番号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="5f48c-169">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="5f48c-170">カナダの社会保険番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-170">Canada Social Insurance Number</span></span>
- <span data-ttu-id="5f48c-171">	チリの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-171">Chile Identity Card Number</span></span>
- <span data-ttu-id="5f48c-172">	中国の居民身分証明書 (PRC) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-172">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="5f48c-173">クレジット カード番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-173">Credit Card Number</span></span>
- <span data-ttu-id="5f48c-174">クロアチアの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-174">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="5f48c-175">クロアチアの個人識別 (OIB) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-175">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="5f48c-176">チェコの個人 ID 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-176">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="5f48c-177">デンマークの個人識別番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-177">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="5f48c-178">麻薬取締局 (DEA) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-178">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="5f48c-179">欧州連合のデビット カード番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-179">EU Debit Card Number</span></span>
- <span data-ttu-id="5f48c-180">EU の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-180">EU Driver's License Number</span></span>  
- <span data-ttu-id="5f48c-181">EU の国民識別番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-181">EU National Identification Number</span></span>  
- <span data-ttu-id="5f48c-182">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-182">EU Passport Number</span></span>  
- <span data-ttu-id="5f48c-183">EU 社会保障番号 (SSN) または同等の ID</span><span class="sxs-lookup"><span data-stu-id="5f48c-183">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="5f48c-184">EU 税 ID 番号 (TIN)</span><span class="sxs-lookup"><span data-stu-id="5f48c-184">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="5f48c-185">フィンランドの国民 ID</span><span class="sxs-lookup"><span data-stu-id="5f48c-185">Finland National ID</span></span>
- <span data-ttu-id="5f48c-186">フィンランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-186">Finland Passport Number</span></span>
- <span data-ttu-id="5f48c-187">フランスの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-187">France Driver's License Number</span></span>
- <span data-ttu-id="5f48c-188">フランスの国民識別カード (CNI)</span><span class="sxs-lookup"><span data-stu-id="5f48c-188">France National ID Card (CNI)</span></span>
- <span data-ttu-id="5f48c-189">フランスのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-189">France Passport Number</span></span>
- <span data-ttu-id="5f48c-190">フランスの社会保障番号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="5f48c-190">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="5f48c-191">ドイツの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-191">German Driver's License Number</span></span>
- <span data-ttu-id="5f48c-192">ドイツのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-192">German Passport Number</span></span>
- <span data-ttu-id="5f48c-193">ドイツの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-193">Germany Identity Card Number</span></span>
- <span data-ttu-id="5f48c-194">ギリシャの国民識別カード</span><span class="sxs-lookup"><span data-stu-id="5f48c-194">Greece National ID Card</span></span>  
- <span data-ttu-id="5f48c-195">香港の ID カード (HKID) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-195">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="5f48c-196">インドの永久口座番号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="5f48c-196">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="5f48c-197">インドの固有識別 (Aadhaar) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-197">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="5f48c-198">インドネシアの身分証明書 (KTP) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-198">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="5f48c-199">国際銀行口座番号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="5f48c-199">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="5f48c-200">国際分類の病気 (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="5f48c-200">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="5f48c-201">国際疾病分類 (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="5f48c-201">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="5f48c-202">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="5f48c-202">IP Address</span></span>
- <span data-ttu-id="5f48c-203">アイルランドの個人公共サービス (PPS) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-203">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="5f48c-204">イスラエルの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-204">Israel Bank Account Number</span></span>
- <span data-ttu-id="5f48c-205">イスラエルの国民 ID</span><span class="sxs-lookup"><span data-stu-id="5f48c-205">Israel National ID</span></span>
- <span data-ttu-id="5f48c-206">イタリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-206">Italy Driver's License Number</span></span>
- <span data-ttu-id="5f48c-207">日本の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-207">Japan Bank Account Number</span></span>
- <span data-ttu-id="5f48c-208">日本の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-208">Japan Driver's License Number</span></span>
- <span data-ttu-id="5f48c-209">日本のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-209">Japan Passport Number</span></span>
- <span data-ttu-id="5f48c-210">日本の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-210">Japan Resident Registration Number</span></span>
- <span data-ttu-id="5f48c-211">日本の社会保険番号 (SIN)</span><span class="sxs-lookup"><span data-stu-id="5f48c-211">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="5f48c-212">日本の在留カード番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-212">Japanese Residence Card Number</span></span>
- <span data-ttu-id="5f48c-213">マレーシアの ID カード番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-213">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="5f48c-214">オランダの市民サービス (BSN) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-214">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="5f48c-215">ニュージーランドの保健省番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-215">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="5f48c-216">ノルウェーの識別番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-216">Norway Identity Number</span></span>  
- <span data-ttu-id="5f48c-217">フィリピンの汎用多目的 ID 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-217">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="5f48c-218">ポーランドの ID カード</span><span class="sxs-lookup"><span data-stu-id="5f48c-218">Poland Identity Card</span></span>
- <span data-ttu-id="5f48c-219">ポーランドの国民 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="5f48c-219">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="5f48c-220">ポーランドのパスポート</span><span class="sxs-lookup"><span data-stu-id="5f48c-220">Poland Passport</span></span>
- <span data-ttu-id="5f48c-221">ポルトガルの市民カード番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-221">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="5f48c-222">サウジアラビアの国民 ID</span><span class="sxs-lookup"><span data-stu-id="5f48c-222">Saudi Arabia National ID</span></span>
- <span data-ttu-id="5f48c-223">シンガポールの国民登録 ID カード (NRIC) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-223">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="5f48c-224">南アフリカの識別番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-224">South Africa Identification Number</span></span>  
- <span data-ttu-id="5f48c-225">韓国の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-225">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="5f48c-226">スペインの社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="5f48c-226">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="5f48c-227">SQL Server接続文字列</span><span class="sxs-lookup"><span data-stu-id="5f48c-227">SQL Server Connection String</span></span>  
- <span data-ttu-id="5f48c-228">スウェーデンの国民 ID</span><span class="sxs-lookup"><span data-stu-id="5f48c-228">Sweden National ID</span></span>
- <span data-ttu-id="5f48c-229">スウェーデンのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-229">Sweden Passport Number</span></span>
- <span data-ttu-id="5f48c-230">SWIFT コード</span><span class="sxs-lookup"><span data-stu-id="5f48c-230">SWIFT Code</span></span>
- <span data-ttu-id="5f48c-231">台湾の国民 ID</span><span class="sxs-lookup"><span data-stu-id="5f48c-231">Taiwan National ID</span></span>
- <span data-ttu-id="5f48c-232">	台湾のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-232">Taiwan Passport Number</span></span>
- <span data-ttu-id="5f48c-233">台湾居住者証明書 (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="5f48c-233">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="5f48c-234">タイの人口識別コード</span><span class="sxs-lookup"><span data-stu-id="5f48c-234">Thai Population Identification Code</span></span>
- <span data-ttu-id="5f48c-235">トルコの国民識別番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-235">Turkish National Identification number</span></span>
- <span data-ttu-id="5f48c-p103">英国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-p103">U.K. Driver's License Number</span></span>
- <span data-ttu-id="5f48c-p104">英国の選挙登録番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-p104">U.K. Electoral Roll Number</span></span>
- <span data-ttu-id="5f48c-p105">英国の国民健康保険番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-p105">U.K. National Health Service Number</span></span>
- <span data-ttu-id="5f48c-p106">英国の国民保険番号 (NINO)</span><span class="sxs-lookup"><span data-stu-id="5f48c-p106">U.K. National Insurance Number (NINO)</span></span>
- <span data-ttu-id="5f48c-244">米国/英国</span><span class="sxs-lookup"><span data-stu-id="5f48c-244">U.S. / U.K.</span></span> <span data-ttu-id="5f48c-245">Passport Number</span><span class="sxs-lookup"><span data-stu-id="5f48c-245">Passport Number</span></span>
- <span data-ttu-id="5f48c-246">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-246">U.S. Bank Account Number</span></span>
- <span data-ttu-id="5f48c-247">米国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-247">U.S. Driver's License Number</span></span>
- <span data-ttu-id="5f48c-248">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="5f48c-248">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="5f48c-249">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="5f48c-249">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="5f48c-250">カスタムの機密情報の種類は、上記の機密情報の種類に加えて、DLP ポリシー のヒントにもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5f48c-250">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="5f48c-251">エンドポイントのデータ損失防止は、一部の機密情報の種類についてのみポリシー ヒントをサポートしています</span><span class="sxs-lookup"><span data-stu-id="5f48c-251">Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="5f48c-252">エンドポイント デバイスに存在するドキュメントで検出される、既定の機密情報の種類の一覧は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5f48c-252">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="5f48c-253">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-253">ABA Routing Number</span></span> 
- <span data-ttu-id="5f48c-254">アルゼンチンの国民識別 (DNI) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-254">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="5f48c-255">オーストラリアの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-255">Australia Bank Account Number</span></span> 
- <span data-ttu-id="5f48c-256">オーストラリアの医療口座番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-256">Australia Medical Account Number</span></span> 
- <span data-ttu-id="5f48c-257">オーストラリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-257">Australia Passport Number</span></span> 
- <span data-ttu-id="5f48c-258">オーストラリアの納税者番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-258">Australia Tax File Number</span></span> 
- <span data-ttu-id="5f48c-259">オーストラリアのビジネス番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-259">Australian Business Number</span></span> 
- <span data-ttu-id="5f48c-260">オーストラリアの会社番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-260">Australian Company Number</span></span> 
- <span data-ttu-id="5f48c-261">オーストリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-261">Austria Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-262">オーストリアの ID カード</span><span class="sxs-lookup"><span data-stu-id="5f48c-262">Austria Identity Card</span></span> 
- <span data-ttu-id="5f48c-263">オーストリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-263">Austria Passport Number</span></span> 
- <span data-ttu-id="5f48c-264">オーストリアの社会保障番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-264">Austria Social Security Number</span></span> 
- <span data-ttu-id="5f48c-265">オーストリアの納税者番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-265">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="5f48c-266">オーストリア付加価値税 (VAT) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-266">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="5f48c-267">Azure DocumentDB Auth Key</span><span class="sxs-lookup"><span data-stu-id="5f48c-267">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="5f48c-268">Azure IAAS データベース接続文字列と Azure SQL接続文字列</span><span class="sxs-lookup"><span data-stu-id="5f48c-268">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="5f48c-269">Azure IoT 接続文字列</span><span class="sxs-lookup"><span data-stu-id="5f48c-269">Azure IoT Connection String</span></span> 
- <span data-ttu-id="5f48c-270">Azure 発行設定パスワード</span><span class="sxs-lookup"><span data-stu-id="5f48c-270">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="5f48c-271">Azure Redis キャッシュ接続文字列</span><span class="sxs-lookup"><span data-stu-id="5f48c-271">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="5f48c-272">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="5f48c-272">Azure SAS</span></span> 
- <span data-ttu-id="5f48c-273">Azure Service Bus 接続文字列</span><span class="sxs-lookup"><span data-stu-id="5f48c-273">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="5f48c-274">Azure ストレージ アカウント キー</span><span class="sxs-lookup"><span data-stu-id="5f48c-274">Azure Storage Account Key</span></span> 
- <span data-ttu-id="5f48c-275">Azure ストレージ アカウント キー (汎用)</span><span class="sxs-lookup"><span data-stu-id="5f48c-275">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="5f48c-276">ベルギーの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-276">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-277">ベルギーの国民番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-277">Belgium National Number</span></span> 
- <span data-ttu-id="5f48c-278">ベルギーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-278">Belgium Passport Number</span></span> 
- <span data-ttu-id="5f48c-279">ベルギーの付加価値税番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-279">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="5f48c-280">ブラジルの CPF 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-280">Brazil CPF Number</span></span> 
- <span data-ttu-id="5f48c-281">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="5f48c-281">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="5f48c-282">	ブラジルの国民識別カード (RG)</span><span class="sxs-lookup"><span data-stu-id="5f48c-282">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="5f48c-283">ブルガリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-283">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-284">ブルガリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-284">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="5f48c-285">ブルガリアの統一市民番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-285">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="5f48c-286">カナダの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-286">Canada Bank Account Number</span></span> 
- <span data-ttu-id="5f48c-287">カナダの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-287">Canada Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-288">カナダの健康保険番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-288">Canada Health Service Number</span></span> 
- <span data-ttu-id="5f48c-289">カナダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-289">Canada Passport Number</span></span> 
- <span data-ttu-id="5f48c-290">カナダの個人保健識別番号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="5f48c-290">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="5f48c-291">カナダの社会保険番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-291">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="5f48c-292">	チリの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-292">Chile Identity Card Number</span></span> 
- <span data-ttu-id="5f48c-293">	中国の居民身分証明書 (PRC) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-293">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="5f48c-294">クレジットカード番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-294">Credit Card Number</span></span> 
- <span data-ttu-id="5f48c-295">クロアチア の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-295">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-296">クロアチアの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-296">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="5f48c-297">クロアチアの国民 ID カード番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-297">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="5f48c-298">クロアチアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-298">Croatia Passport Number</span></span> 
- <span data-ttu-id="5f48c-299">クロアチアの個人識別 (OIB) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-299">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="5f48c-300">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span><span class="sxs-lookup"><span data-stu-id="5f48c-300">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="5f48c-301">CSCAN-GENERAL0140 一般対称キー</span><span class="sxs-lookup"><span data-stu-id="5f48c-301">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="5f48c-302">キプロス の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-302">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-303">キプロスの ID カード</span><span class="sxs-lookup"><span data-stu-id="5f48c-303">Cyprus Identity Card</span></span> 
- <span data-ttu-id="5f48c-304">キプロスのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-304">Cyprus Passport Number</span></span> 
- <span data-ttu-id="5f48c-305">キプロスの納税者番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-305">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="5f48c-306">チェコの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-306">Czech Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-307">チェコの個人 ID 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-307">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="5f48c-308">チェコ共和国のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-308">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="5f48c-309">デンマークの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-309">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-310">デンマークのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-310">Denmark Passport Number</span></span> 
- <span data-ttu-id="5f48c-311">デンマークの個人識別番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-311">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="5f48c-312">麻薬取締局 (DEA) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-312">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="5f48c-313">エストニア の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-313">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-314">エストニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-314">Estonia Passport Number</span></span> 
- <span data-ttu-id="5f48c-315">エストニアの個人識別コード</span><span class="sxs-lookup"><span data-stu-id="5f48c-315">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="5f48c-316">欧州連合のデビット カード番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-316">EU Debit Card Number</span></span> 
- <span data-ttu-id="5f48c-317">EU の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-317">EU Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-318">EU の国民識別番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-318">EU National Identification Number</span></span> 
- <span data-ttu-id="5f48c-319">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-319">EU Passport Number</span></span> 
- <span data-ttu-id="5f48c-320">EU 社会保障番号 (SSN) または同等の ID</span><span class="sxs-lookup"><span data-stu-id="5f48c-320">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="5f48c-321">EU 税 ID 番号 (TIN)</span><span class="sxs-lookup"><span data-stu-id="5f48c-321">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="5f48c-322">フィンランド の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-322">Finland Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-323">フィンランド のヨーロッパの健康保険番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-323">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="5f48c-324">フィンランドの国民 ID</span><span class="sxs-lookup"><span data-stu-id="5f48c-324">Finland National ID</span></span> 
- <span data-ttu-id="5f48c-325">フィンランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-325">Finland Passport Number</span></span> 
- <span data-ttu-id="5f48c-326">フランスの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-326">France Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-327">フランスの健康保険番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-327">France Health Insurance Number</span></span> 
- <span data-ttu-id="5f48c-328">フランスの国民識別カード (CNI)</span><span class="sxs-lookup"><span data-stu-id="5f48c-328">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="5f48c-329">フランスのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-329">France Passport Number</span></span> 
- <span data-ttu-id="5f48c-330">フランスの社会保障番号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="5f48c-330">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="5f48c-331">フランスの納税者番号 (numéro SPI.)</span><span class="sxs-lookup"><span data-stu-id="5f48c-331">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="5f48c-332">フランスの付加価値税番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-332">France Value Added Tax Number</span></span> 
- <span data-ttu-id="5f48c-333">ドイツの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-333">German Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-334">ドイツのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-334">German Passport Number</span></span> 
- <span data-ttu-id="5f48c-335">ドイツの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-335">Germany Identity Card Number</span></span> 
- <span data-ttu-id="5f48c-336">ドイツの納税者番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-336">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="5f48c-337">ドイツの付加価値税番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-337">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="5f48c-338">ギリシャの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-338">Greece Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-339">ギリシャの国民識別カード</span><span class="sxs-lookup"><span data-stu-id="5f48c-339">Greece National ID Card</span></span> 
- <span data-ttu-id="5f48c-340">ギリシャのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-340">Greece Passport Number</span></span> 
- <span data-ttu-id="5f48c-341">ギリシャの社会保障番号 (AMKA)</span><span class="sxs-lookup"><span data-stu-id="5f48c-341">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="5f48c-342">ギリシャ語の税の識別番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-342">Greek Tax identification Number</span></span> 
- <span data-ttu-id="5f48c-343">香港の ID カード (HKID) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-343">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="5f48c-344">ハンガリーの社会保障番号 (TAJ)</span><span class="sxs-lookup"><span data-stu-id="5f48c-344">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="5f48c-345">ハンガリーの付加価値税番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-345">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="5f48c-346">ハンガリー の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-346">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-347">ハンガリーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-347">Hungary Passport Number</span></span> 
- <span data-ttu-id="5f48c-348">ハンガリーの個人識別番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-348">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="5f48c-349">ハンガリー 税の識別番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-349">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="5f48c-350">インドの永久口座番号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="5f48c-350">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="5f48c-351">インドの固有識別 (Aadhaar) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-351">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="5f48c-352">インドネシアの身分証明書 (KTP) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-352">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="5f48c-353">国際銀行口座番号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="5f48c-353">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="5f48c-354">国際分類の病気 (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="5f48c-354">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="5f48c-355">国際疾病分類 (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="5f48c-355">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="5f48c-356">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="5f48c-356">IP Address</span></span> 
- <span data-ttu-id="5f48c-357">アイルランドの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-357">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-358">アイルランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-358">Ireland Passport Number</span></span> 
- <span data-ttu-id="5f48c-359">アイルランドの個人公共サービス (PPS) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-359">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="5f48c-360">イスラエルの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-360">Israel Bank Account Number</span></span> 
- <span data-ttu-id="5f48c-361">イスラエルの国民 ID</span><span class="sxs-lookup"><span data-stu-id="5f48c-361">Israel National ID</span></span> 
- <span data-ttu-id="5f48c-362">イタリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-362">Italy Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-363">イタリアの会計コード</span><span class="sxs-lookup"><span data-stu-id="5f48c-363">Italy Fiscal Code</span></span> 
- <span data-ttu-id="5f48c-364">イタリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-364">Italy Passport Number</span></span> 
- <span data-ttu-id="5f48c-365">イタリアの付加価値税番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-365">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="5f48c-366">日本の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-366">Japan Bank Account Number</span></span> 
- <span data-ttu-id="5f48c-367">日本の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-367">Japan Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-368">日本のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-368">Japan Passport Number</span></span> 
- <span data-ttu-id="5f48c-369">日本の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-369">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="5f48c-370">日本の社会保険番号 (SIN)</span><span class="sxs-lookup"><span data-stu-id="5f48c-370">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="5f48c-371">日本語 My Number Corporate</span><span class="sxs-lookup"><span data-stu-id="5f48c-371">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="5f48c-372">日本語の個人用番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-372">Japanese My Number Personal</span></span> 
- <span data-ttu-id="5f48c-373">日本の在留カード番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-373">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="5f48c-374">ラトビア の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-374">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-375">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-375">Latvia Passport Number</span></span> 
- <span data-ttu-id="5f48c-376">ラトビアの個人コード</span><span class="sxs-lookup"><span data-stu-id="5f48c-376">Latvia Personal Code</span></span> 
- <span data-ttu-id="5f48c-377">リトアニア の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-377">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-378">リトアニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-378">Lithuania Passport Number</span></span> 
- <span data-ttu-id="5f48c-379">リトアニア の個人用コード</span><span class="sxs-lookup"><span data-stu-id="5f48c-379">Lithuania Personal Code</span></span> 
- <span data-ttu-id="5f48c-380">ルクセンブルク 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-380">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-381">ルクセンブルク国民識別番号 (自然人)</span><span class="sxs-lookup"><span data-stu-id="5f48c-381">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="5f48c-382">ルクセンブルク国民識別番号 (非自然人)</span><span class="sxs-lookup"><span data-stu-id="5f48c-382">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="5f48c-383">ルクセンブルク パスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-383">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="5f48c-384">マレーシアの ID カード番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-384">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="5f48c-385">マルタの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-385">Malta Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-386">マルタの ID カード番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-386">Malta Identity Card Number</span></span> 
- <span data-ttu-id="5f48c-387">マルタのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-387">Malta Passport Number</span></span> 
- <span data-ttu-id="5f48c-388">マルタ税 ID 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-388">Malta Tax ID Number</span></span> 
- <span data-ttu-id="5f48c-389">オランダの市民サービス (BSN) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-389">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="5f48c-390">オランダの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-390">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-391">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-391">Netherlands Passport Number</span></span> 
- <span data-ttu-id="5f48c-392">オランダの納税者番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-392">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="5f48c-393">オランダの付加価値税番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-393">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="5f48c-394">ニュージーランドの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-394">New Zealand bank account number</span></span> 
- <span data-ttu-id="5f48c-395">ニュージーランドの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-395">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="5f48c-396">ニュージーランド 内陸の収益番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-396">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="5f48c-397">ニュージーランドの保健省番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-397">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="5f48c-398">ニュージーランドのソーシャル 福利厚生番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-398">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="5f48c-399">ノルウェーの識別番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-399">Norway Identity Number</span></span> 
- <span data-ttu-id="5f48c-400">フィリピンの汎用多目的 ID 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-400">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="5f48c-401">ポーランド の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-401">Poland Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-402">ポーランドの ID カード</span><span class="sxs-lookup"><span data-stu-id="5f48c-402">Poland Identity Card</span></span> 
- <span data-ttu-id="5f48c-403">ポーランドの国民 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="5f48c-403">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="5f48c-404">ポーランドのパスポート</span><span class="sxs-lookup"><span data-stu-id="5f48c-404">Poland Passport</span></span> 
- <span data-ttu-id="5f48c-405">ポーランドの納税者番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-405">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="5f48c-406">ポーランド語 REGON 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-406">Polish REGON Number</span></span> 
- <span data-ttu-id="5f48c-407">ポルトガルの市民カード番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-407">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="5f48c-408">ポルトガルの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-408">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-409">ポルトガルのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-409">Portugal Passport Number</span></span> 
- <span data-ttu-id="5f48c-410">ポルトガルの納税者番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-410">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="5f48c-411">ルーマニアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-411">Romania Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-412">ルーマニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-412">Romania Passport Number</span></span> 
- <span data-ttu-id="5f48c-413">ルーマニア の個人数値コード (CNP)</span><span class="sxs-lookup"><span data-stu-id="5f48c-413">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="5f48c-414">ロシアのパスポート番号 (国内)</span><span class="sxs-lookup"><span data-stu-id="5f48c-414">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="5f48c-415">ロシアのパスポート番号 (国際)</span><span class="sxs-lookup"><span data-stu-id="5f48c-415">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="5f48c-416">サウジアラビアの国民 ID</span><span class="sxs-lookup"><span data-stu-id="5f48c-416">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="5f48c-417">シンガポールの国民登録 ID カード (NRIC) 番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-417">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="5f48c-418">スロバキアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-418">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-419">スロバキアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-419">Slovakia Passport Number</span></span> 
- <span data-ttu-id="5f48c-420">スロバキアの個人番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-420">Slovakia Personal Number</span></span> 
- <span data-ttu-id="5f48c-421">スロベニア の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-421">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-422">スロベニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-422">Slovenia Passport Number</span></span> 
- <span data-ttu-id="5f48c-423">スロベニアの納税者番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-423">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="5f48c-424">スロベニアの一意のマスター市民番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-424">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="5f48c-425">南アフリカの識別番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-425">South Africa Identification Number</span></span> 
- <span data-ttu-id="5f48c-426">韓国の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-426">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="5f48c-427">スペイン DNI</span><span class="sxs-lookup"><span data-stu-id="5f48c-427">Spain DNI</span></span> 
- <span data-ttu-id="5f48c-428">スペインの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-428">Spain Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-429">スペインのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-429">Spain Passport Number</span></span> 
- <span data-ttu-id="5f48c-430">スペインの社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="5f48c-430">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="5f48c-431">スペインの納税者番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-431">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="5f48c-432">SQL Server接続文字列</span><span class="sxs-lookup"><span data-stu-id="5f48c-432">SQL Server Connection String</span></span> 
- <span data-ttu-id="5f48c-433">スウェーデンの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-433">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-434">スウェーデンの国民 ID</span><span class="sxs-lookup"><span data-stu-id="5f48c-434">Sweden National ID</span></span> 
- <span data-ttu-id="5f48c-435">スウェーデンのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-435">Sweden Passport Number</span></span> 
- <span data-ttu-id="5f48c-436">スウェーデンの納税者番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-436">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="5f48c-437">SWIFT コード</span><span class="sxs-lookup"><span data-stu-id="5f48c-437">SWIFT Code</span></span> 
- <span data-ttu-id="5f48c-438">スイスの社会保障番号 AHV</span><span class="sxs-lookup"><span data-stu-id="5f48c-438">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="5f48c-439">台湾の国民 ID</span><span class="sxs-lookup"><span data-stu-id="5f48c-439">Taiwan National ID</span></span> 
- <span data-ttu-id="5f48c-440">	台湾のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-440">Taiwan Passport Number</span></span> 
- <span data-ttu-id="5f48c-441">台湾居住者証明書 (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="5f48c-441">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="5f48c-442">タイの人口識別コード</span><span class="sxs-lookup"><span data-stu-id="5f48c-442">Thai Population Identification Code</span></span> 
- <span data-ttu-id="5f48c-443">トルコの国民識別番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-443">Turkish National Identification number</span></span> 
- <span data-ttu-id="5f48c-p108">英国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-p108">U.K. Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-p109">英国の選挙登録番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-p109">U.K. Electoral Roll Number</span></span> 
- <span data-ttu-id="5f48c-p110">英国の国民健康保険番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-p110">U.K. National Health Service Number</span></span> 
- <span data-ttu-id="5f48c-p111">英国の国民保険番号 (NINO)</span><span class="sxs-lookup"><span data-stu-id="5f48c-p111">U.K. National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="5f48c-452">英国</span><span class="sxs-lookup"><span data-stu-id="5f48c-452">U.K.</span></span> <span data-ttu-id="5f48c-453">一意の納税者参照番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-453">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="5f48c-454">米国/英国</span><span class="sxs-lookup"><span data-stu-id="5f48c-454">U.S. / U.K.</span></span> <span data-ttu-id="5f48c-455">Passport Number</span><span class="sxs-lookup"><span data-stu-id="5f48c-455">Passport Number</span></span> 
- <span data-ttu-id="5f48c-456">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-456">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="5f48c-457">米国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="5f48c-457">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="5f48c-458">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="5f48c-458">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="5f48c-459">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="5f48c-459">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="5f48c-460">ウクライナのパスポート番号 (国内)</span><span class="sxs-lookup"><span data-stu-id="5f48c-460">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="5f48c-461">ウクライナのパスポート番号 (国際)</span><span class="sxs-lookup"><span data-stu-id="5f48c-461">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="5f48c-462">上記の機密情報の種類に加えて、カスタムの機密情報の種類も検出されます。</span><span class="sxs-lookup"><span data-stu-id="5f48c-462">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="5f48c-463">Microsoft アプリ全体の DLP ポリシー ヒントのサポート マトリックス</span><span class="sxs-lookup"><span data-stu-id="5f48c-463">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="5f48c-464">**アプリとプラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="5f48c-464">**App and platform**</span></span>|<span data-ttu-id="5f48c-465">**DLP ポリシー ヒントのサポート**</span><span class="sxs-lookup"><span data-stu-id="5f48c-465">**DLP policy tip support**</span></span>|<span data-ttu-id="5f48c-466">**サポートされる機密情報の種類**</span><span class="sxs-lookup"><span data-stu-id="5f48c-466">**Sensitive information types supported**</span></span>|<span data-ttu-id="5f48c-467">**サポートされる述語とアクション**</span><span class="sxs-lookup"><span data-stu-id="5f48c-467">**Predicates and actions supported**</span></span>|<span data-ttu-id="5f48c-468">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5f48c-468">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="5f48c-469">**Outlook Web Access**</span><span class="sxs-lookup"><span data-stu-id="5f48c-469">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="5f48c-470">すべて</span><span class="sxs-lookup"><span data-stu-id="5f48c-470">All</span></span>|<span data-ttu-id="5f48c-471">Subset</span><span class="sxs-lookup"><span data-stu-id="5f48c-471">Subset</span></span>|<span data-ttu-id="5f48c-472">「 [データ損失防止ポリシー のヒントリファレンス」を参照してください。](#data-loss-prevention-policy-tips-reference)</span><span class="sxs-lookup"><span data-stu-id="5f48c-472">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="5f48c-473">**Outlook Win32 (Outlook 2013 以降)**</span><span class="sxs-lookup"><span data-stu-id="5f48c-473">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="5f48c-474">Subset</span><span class="sxs-lookup"><span data-stu-id="5f48c-474">Subset</span></span>|<span data-ttu-id="5f48c-475">Subset</span><span class="sxs-lookup"><span data-stu-id="5f48c-475">Subset</span></span>|<span data-ttu-id="5f48c-476">[Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions)以降では、一部の条件と例外に関するポリシー ヒントの表示をサポートし[、Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types)以降では、Outlook Win32 で DLP ポリシー ヒントを表示するためにサポートされる機密情報の種類と DLP 条件とアクションのサポートの詳細については、一部の機密情報の種類に関するポリシー ヒントのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5f48c-476">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later supports showing policy tips for only some sensitive information types](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="5f48c-477">**Outlook Mobile (iOS、Android)/Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="5f48c-477">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="5f48c-478">なし</span><span class="sxs-lookup"><span data-stu-id="5f48c-478">None</span></span>|<span data-ttu-id="5f48c-479">なし</span><span class="sxs-lookup"><span data-stu-id="5f48c-479">None</span></span>|<span data-ttu-id="5f48c-480">DLP ポリシー のヒントは Outlook モバイルではサポートされていません</span><span class="sxs-lookup"><span data-stu-id="5f48c-480">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="5f48c-481">**Sharepoint Online/One Drive for Business Web クライアント**</span><span class="sxs-lookup"><span data-stu-id="5f48c-481">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="5f48c-482">すべて</span><span class="sxs-lookup"><span data-stu-id="5f48c-482">All</span></span>|<span data-ttu-id="5f48c-483">DLP のすべての SPO/ODB 述語とアクション</span><span class="sxs-lookup"><span data-stu-id="5f48c-483">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="5f48c-484">**Sharepoint Win32/ One Drive for Business Win32 クライアント**</span><span class="sxs-lookup"><span data-stu-id="5f48c-484">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="5f48c-485">なし</span><span class="sxs-lookup"><span data-stu-id="5f48c-485">None</span></span>|<span data-ttu-id="5f48c-486">なし</span><span class="sxs-lookup"><span data-stu-id="5f48c-486">None</span></span>|<span data-ttu-id="5f48c-487">Sharepoint または OneDrive デスクトップ クライアント アプリでは DLP ポリシーのヒントはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="5f48c-487">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="5f48c-488">**Word、Excel、Powerpoint Web クライアント**</span><span class="sxs-lookup"><span data-stu-id="5f48c-488">**Word, Excel, Powerpoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="5f48c-489">すべて</span><span class="sxs-lookup"><span data-stu-id="5f48c-489">All</span></span>|<span data-ttu-id="5f48c-490">DLP のすべての SPO/ODB 述語とアクション</span><span class="sxs-lookup"><span data-stu-id="5f48c-490">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="5f48c-491">DLP ポリシー ヒントは、ドキュメントが SPO または ODB Web アプリでホストされ、DLP ポリシーが既にスタンプされている場合にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5f48c-491">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="5f48c-492">**Word、Excel、Powerpoint モバイル クライアント**</span><span class="sxs-lookup"><span data-stu-id="5f48c-492">**Word, Excel, Powerpoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="5f48c-493">なし</span><span class="sxs-lookup"><span data-stu-id="5f48c-493">None</span></span>|<span data-ttu-id="5f48c-494">なし</span><span class="sxs-lookup"><span data-stu-id="5f48c-494">None</span></span>|<span data-ttu-id="5f48c-495">DLP ポリシー のヒントは、モバイル アプリではサポートされていません。Office。</span><span class="sxs-lookup"><span data-stu-id="5f48c-495">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="5f48c-496">**Teams Web/ Teams デスクトップ/ Teams Mobile/ Teams Mac**</span><span class="sxs-lookup"><span data-stu-id="5f48c-496">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="5f48c-497">すべて</span><span class="sxs-lookup"><span data-stu-id="5f48c-497">All</span></span>|<span data-ttu-id="5f48c-498">DLP ポリシーのすべての Teams 述語</span><span class="sxs-lookup"><span data-stu-id="5f48c-498">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="5f48c-499">ポリシー ヒントは、メッセージに "このメッセージのフラグが設定されています" というフラグが付けらた場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f48c-499">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="5f48c-500">何が可能ですか?</span><span class="sxs-lookup"><span data-stu-id="5f48c-500">What can I do?”</span></span> <span data-ttu-id="5f48c-501">リンクをクリックすると、ユーザーは検出された機密情報の種類を確認し、管理者が許可した場合に問題を上書きまたは報告できます。ファイルに関するポリシー ヒントは表示されません。</span><span class="sxs-lookup"><span data-stu-id="5f48c-501">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="5f48c-502">受信者がドキュメントにアクセスしようとすると、許可されていない場合にアクセスが拒否される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5f48c-502">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="5f48c-503">**Win32 Endpoint Devices**</span><span class="sxs-lookup"><span data-stu-id="5f48c-503">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="5f48c-504">Subset</span><span class="sxs-lookup"><span data-stu-id="5f48c-504">Subset</span></span>|<span data-ttu-id="5f48c-505">DLP ポリシーのすべてのエンドポイント DLP 述語とアクション</span><span class="sxs-lookup"><span data-stu-id="5f48c-505">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="5f48c-506">「 [エンドポイントのデータ損失防止は、一部の機密情報の種類についてのみポリシー ヒントをサポートしています」を参照してください。](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="5f48c-506">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="5f48c-507">**Mac デバイス**</span><span class="sxs-lookup"><span data-stu-id="5f48c-507">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="5f48c-508">なし</span><span class="sxs-lookup"><span data-stu-id="5f48c-508">None</span></span>|<span data-ttu-id="5f48c-509">なし</span><span class="sxs-lookup"><span data-stu-id="5f48c-509">None</span></span>|<span data-ttu-id="5f48c-510">データ損失防止は、今日の Mac デバイスでは強制できません</span><span class="sxs-lookup"><span data-stu-id="5f48c-510">Data loss prevention are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="5f48c-511">**サードパーティのクラウド アプリ**</span><span class="sxs-lookup"><span data-stu-id="5f48c-511">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="5f48c-512">なし</span><span class="sxs-lookup"><span data-stu-id="5f48c-512">None</span></span>|<span data-ttu-id="5f48c-513">なし</span><span class="sxs-lookup"><span data-stu-id="5f48c-513">None</span></span>|<span data-ttu-id="5f48c-514">データ損失防止</span><span class="sxs-lookup"><span data-stu-id="5f48c-514">Data Loss Prevention</span></span>|
|<span data-ttu-id="5f48c-515">**On-prem**</span><span class="sxs-lookup"><span data-stu-id="5f48c-515">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="5f48c-516">なし</span><span class="sxs-lookup"><span data-stu-id="5f48c-516">None</span></span>|<span data-ttu-id="5f48c-517">なし</span><span class="sxs-lookup"><span data-stu-id="5f48c-517">None</span></span>||
|<span data-ttu-id="5f48c-518">**Word、Excel、Powerpoint Win32 クライアント**</span><span class="sxs-lookup"><span data-stu-id="5f48c-518">**Word, Excel, Powerpoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="5f48c-519">Subset</span><span class="sxs-lookup"><span data-stu-id="5f48c-519">Subset</span></span>|<span data-ttu-id="5f48c-520">Subset</span><span class="sxs-lookup"><span data-stu-id="5f48c-520">Subset</span></span>|<span data-ttu-id="5f48c-521">WXP クライアント アプリのポリシー ヒントは、以下または DLP ポリシー内の条件またはアクションのサブセットを正確に持つすべての DLP ポリシーについて、Sharepoint Online または One Drive for Business Sites に保存されているドキュメントで機能します。</span><span class="sxs-lookup"><span data-stu-id="5f48c-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="5f48c-522">コンテンツには機密情報の種類が含まれる</span><span class="sxs-lookup"><span data-stu-id="5f48c-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="5f48c-523">Access Scope (コンテンツは内部/外部で共有されます)</span><span class="sxs-lookup"><span data-stu-id="5f48c-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="5f48c-524">ユーザーに通知する (ポリシー ヒント/ユーザー通知)</span><span class="sxs-lookup"><span data-stu-id="5f48c-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="5f48c-525">すべてのユーザーをブロックする</span><span class="sxs-lookup"><span data-stu-id="5f48c-525">Block everyone</span></span></li><li><span data-ttu-id="5f48c-526">インシデント レポート</span><span class="sxs-lookup"><span data-stu-id="5f48c-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="5f48c-527">その他の条件またはアクションが存在する場合、そのポリシーの DLP ポリシー ヒントは、Word、Excel、または PowerPoint のデスクトップ アプリには表示されません。</span><span class="sxs-lookup"><span data-stu-id="5f48c-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span>|
||||||