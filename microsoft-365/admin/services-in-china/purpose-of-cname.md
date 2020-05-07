---
title: MSOID の Office 365 CNAME レコードの目的
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Office 365 の ' MSOID ' CNAME レコードの詳細については、「認証プロセスのための最適なサーバー」を参照してください。このため、応答が高速になります。
monikerRange: o365-21vianet
ms.openlocfilehash: a7c59829419ac8e7db400b079681ccf5bff199d6
ms.sourcegitcommit: 83f980927728bc080f97a3e6dc70dc305f3df841
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44053850"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>MSOID の Office 365 CNAME レコードの目的

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
> [!NOTE]
> 以下は、21Vianet が運用している * * Office 365 にのみ適用されます。
  
Office 365 で "MSOID" という CNAME レコードを追加する必要がある理由について疑問に思うかもしれません。 このレコードは、どのサブスクリプションを使っているかにかかわらず、すべてのカスタム ドメインに対して追加する必要のあるものです。 なぜ必要なのでしょうか。 少し技術的になりますが、基本的には、特定の認証プロセスに最適なサーバーに向かわせるためです。このようにして、迅速な応答を得ることができます。
  
技術的な詳細: Office 365、Skype for Business Online、Outlook、Windows PowerShell Active Directory 同期ツールのような Microsoft Azure と連携するクライアント アプリケーションを実行するとき、資格情報が認証される必要があります。Office 365 では、CNAME レコードを使用して、ユーザーの場所に対して適切な認証エンドポイントをポイントすると、迅速な認証応答時間を実現します。
  
ユーザーのドメイン用の CNAME レコードが見つからない場合、これらのアプリケーションは米国の既定の認証エンドポイントを使用します。つまり、認証が遅くなります。この CNAME レコードが正しく構成されていない場合、たとえば [ **宛先またはポイント先のアドレス**] に入力ミスがある場合、これらのアプリケーションは認証できません。
  
 **Office 365 がドメインの DNS レコードを管理している場合は、** Office 365 は、この CNAME レコードを設定します。 
  
 Dns**ホストでドメインの dns レコードを管理している場合**は、 [dns ホストの指示に従っ](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)て自分でこのレコードを作成します。
  
Office 365 の展開を計画していて、追加または更新する必要があるすべての DNS レコードの詳細については、「 [office 365 用の外部ドメインネームシステムレコード](https://go.microsoft.com/fwlink/?LinkId=579013)」を参照してください。
  

