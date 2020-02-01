---
title: 検疫
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9eecdde-dcc2-4283-a820-98d1e740e4f
ms.collection:
- M365-security-compliance
description: Exchange Online および Exchange Online Protection のホストされた検疫について説明します。
ms.openlocfilehash: bcbd0db1c05834882c464fa28012b82a13929d7f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598654"
---
# <a name="quarantine"></a><span data-ttu-id="4463a-103">Quarantine</span><span class="sxs-lookup"><span data-stu-id="4463a-103">Quarantine</span></span>

<span data-ttu-id="4463a-104">次のトピックでは、Exchange Online と Exchange Online Protection (EOP) の管理者およびエンド ユーザーの両方のためにホストされる検疫について説明します</span><span class="sxs-lookup"><span data-stu-id="4463a-104">The following topics provide information about the hosted quarantine for both Exchange Online and Exchange Online Protection (EOP) admins and end users:</span></span>

- <span data-ttu-id="4463a-105">[検疫に関する FAQ](quarantine-faq.md) - 管理者およびエンド ユーザーの両方のための検疫に関する一般的な質問と回答を提供します。</span><span class="sxs-lookup"><span data-stu-id="4463a-105">[Quarantine FAQ](quarantine-faq.md) - Provides general questions and answers about the quarantine for both admins and end users</span></span>

- <span data-ttu-id="4463a-106">[管理者として検疫済みメッセージを検索して解放](find-and-release-quarantined-messages-as-an-administrator.md)する: 管理者が Exchange 管理センター (EAC) 内の検疫にあるメッセージを検索して解放し、必要に応じて、そのメッセージを誤検知 (迷惑メールではない) メッセージとして Microsoft に報告する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4463a-106">[Find and release quarantined messages as an administrator](find-and-release-quarantined-messages-as-an-administrator.md): Describes how admins can find and release any message that resides in the quarantine in the Exchange admin center (EAC), and optionally report it as a false positive (not junk) message to Microsoft.</span></span>

- <span data-ttu-id="4463a-107">[Office のユーザーとして検疫済みメッセージを検索して解放する 365](find-and-release-quarantined-messages-as-a-user.md): エンドユーザーが、スパム検疫のユーザーインターフェイスで自分のスパム検疫メッセージを検索して解放し、それらを迷惑メールではないとして Microsoft に報告する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4463a-107">[Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md): Describes how end users can find and release their own spam-quarantined messages in the spam quarantine user interface, and report them as not junk to Microsoft.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="4463a-108">エンドユーザーのスパム検疫にアクセスするには、エンドユーザーが有効な Office 365 ユーザー ID とパスワードを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4463a-108">In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="4463a-109">社内メールボックスを保護している EOP のお客様は、ディレクトリ同期または EAC を使用して作成された有効な電子メールユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4463a-109">EOP customers protecting on-premises mailboxes must be valid email users created via directory synchronization or the EAC.</span></span> <span data-ttu-id="4463a-110">ユーザーの管理の詳細については、EOP 管理者が[EOP でメールユーザーを管理](manage-mail-users-in-eop.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4463a-110">For more information about managing users, EOP admins can refer to [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="4463a-111">EOP スタンドアロンのお客様の場合は、ディレクトリ同期を使用し、ディレクトリベースのエッジブロックを有効にすることをお勧めします。詳細については、「[ディレクトリベースのエッジブロックを使用して無効な受信者に送信されたメッセージを拒否する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4463a-111">For EOP standalone customers, we recommend using directory synchronization and enabling Directory Based Edge Blocking; for more information, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>
