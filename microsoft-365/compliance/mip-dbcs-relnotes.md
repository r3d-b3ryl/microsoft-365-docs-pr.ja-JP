---
title: 2 バイト文字セットのリリース ノート向け Microsoft 365 コンプライアンス サポート (プレビュー)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 2 バイト文字セットをサポートするためのリリース ノートです。
ms.openlocfilehash: 1c2244c49a92aa2c00fad06caa8194cf7e32220e
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681503"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a><span data-ttu-id="d6b83-103">2 バイト文字セットのリリース ノート向けサポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d6b83-103">Support for double byte character set release notes (preview)</span></span>

 <span data-ttu-id="d6b83-104">Microsoft 365 の情報保護は、次のような場合に 2 バイト文字セットの言語をプレビューでサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d6b83-104">Microsoft 365 Information Protection now supports in preview double byte character set languages for:</span></span>

- <span data-ttu-id="d6b83-105">中国語 (簡体字)</span><span class="sxs-lookup"><span data-stu-id="d6b83-105">Chinese (simplified)</span></span>
- <span data-ttu-id="d6b83-106">中国語 (繁体字)</span><span class="sxs-lookup"><span data-stu-id="d6b83-106">Chinese (traditional)</span></span>
- <span data-ttu-id="d6b83-107">韓国語</span><span class="sxs-lookup"><span data-stu-id="d6b83-107">Korean</span></span>
- <span data-ttu-id="d6b83-108">日本語</span><span class="sxs-lookup"><span data-stu-id="d6b83-108">Japanese</span></span>

<span data-ttu-id="d6b83-109">このサポートは、機密情報の種類とキーワード ディクショナリで使用でき、データ損失防止、通信コンプライアンス、Exchange Online、SharePoint Online、OneDrive for Business、および Teams ソリューションに反映されます。</span><span class="sxs-lookup"><span data-stu-id="d6b83-109">This support is available for sensitive information types and keyword dictionaries and will be reflected in data loss prevention, communications compliance, Exchange Online, SharePoint Online, OneDrive for Business, and Teams solutions.</span></span>

## <a name="known-issues"></a><span data-ttu-id="d6b83-110">既知の問題</span><span class="sxs-lookup"><span data-stu-id="d6b83-110">Known issues</span></span>

- <span data-ttu-id="d6b83-111">メールに添付されているテキスト ファイルが、バイト オーダー マーク (BOM) なしの UTF-8 形式である場合、そのメールは通信コンプライアンス ポリシーで検出されません。</span><span class="sxs-lookup"><span data-stu-id="d6b83-111">When a text file attached to an email is in UTF-8 format without byte order mark (BOM), the email is not detected by the Communication Compliance policy.</span></span>

- <span data-ttu-id="d6b83-112">「メッセージに次のいずれかの単語が含まれている」というポリシー条件に対して、文が入力されている場合、通信コンプライアンス ポリシーで値を検出することはできません。</span><span class="sxs-lookup"><span data-stu-id="d6b83-112">Communication Compliance policies cannot detect values if a sentence is entered for the policy condition: “Message contains any of these words”.</span></span> <span data-ttu-id="d6b83-113">ポリシーで指定したテキストが単語として書かれている場合は検出されますが、文章の途中に書かれている場合は検出されません。</span><span class="sxs-lookup"><span data-stu-id="d6b83-113">If the text specified in the policy is written as a word, it can be detected; however, if it is written in the middle of a sentence, it will not be detected.</span></span>

- <span data-ttu-id="d6b83-114">ディクショナリをタイプ情報として指定する通信コンプライアンス ポリシーでは、Teams のプライベート チャットやチャネル チャットは検出されません。</span><span class="sxs-lookup"><span data-stu-id="d6b83-114">Communication Compliance policies that specify dictionaries as type information do not detect Teams private chats and channel chats.</span></span>

- <span data-ttu-id="d6b83-115">この段階では、次の条件は通信コンプライアンスをサポートしていません (将来的にはこのような問題を修正する予定です)。</span><span class="sxs-lookup"><span data-stu-id="d6b83-115">The following conditions are not supported for Communication Compliance at this stage (we plan to fix these issues in the future):</span></span> 
  - <span data-ttu-id="d6b83-116">「メッセージに次のいずれかの単語が含まれている」</span><span class="sxs-lookup"><span data-stu-id="d6b83-116">“Message contains any of these words”</span></span>
  - <span data-ttu-id="d6b83-117">「メッセージに次のどの単語も含まれていない」</span><span class="sxs-lookup"><span data-stu-id="d6b83-117">“Message contains none of these words”</span></span>
  - <span data-ttu-id="d6b83-118">「添付ファイルに次のいずれかの単語が含まれている」</span><span class="sxs-lookup"><span data-stu-id="d6b83-118">“Attachment contains any of these words”</span></span>
  - <span data-ttu-id="d6b83-119">「添付ファイルに次のいずれかの単語が含まれている」</span><span class="sxs-lookup"><span data-stu-id="d6b83-119">“Attachment contains any of these words”</span></span>

<span data-ttu-id="d6b83-120">代わりに、ユーザー設定の機密情報の種類 (SIT) を作成することをお勧めします。これは、メッセージと添付ファイル全体のパターンを検出し、通信コンプライアンス ポリシーの条件として使用します。</span><span class="sxs-lookup"><span data-stu-id="d6b83-120">Instead we recommend creating a custom Sensitive Information Type (SIT) with keyword dictionary which will detect patterns across messages and attachments, and using this custom SIT as a Communication Compliance policy condition.</span></span>
