---
title: MSOID の Office 365 CNAME レコードの目的
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: 認証プロセスに最適なサーバーに移動する Office 365 の 'MSOID' CNAME レコードの詳細については、応答を速くします。
monikerRange: o365-21vianet
ms.openlocfilehash: e51847065ac3f91f44b8be35932869e9418e8a70
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60188795"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>MSOID の Office 365 CNAME レコードの目的

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
> [!NOTE]
> 次に示すのは、21Vianet がOffice 365 **Office 365に適用されます。
  
Office 365 で "MSOID" という CNAME レコードを追加する必要がある理由について疑問に思うかもしれません。 このレコードは、どのサブスクリプションを使っているかにかかわらず、すべてのカスタム ドメインに対して追加する必要のあるものです。 なぜ必要なのでしょうか。 少し技術的になりますが、基本的には、特定の認証プロセスに最適なサーバーに向かわせるためです。このようにして、迅速な応答を得ることができます。
  
技術的な詳細: Office 365、Skype for Business Online、Outlook、Windows PowerShell Active Directory 同期ツールのような Microsoft Azure と連携するクライアント アプリケーションを実行するとき、資格情報が認証される必要があります。Office 365 では、CNAME レコードを使用して、ユーザーの場所に対して適切な認証エンドポイントをポイントすると、迅速な認証応答時間を実現します。
  
ユーザーのドメイン用の CNAME レコードが見つからない場合、これらのアプリケーションは米国の既定の認証エンドポイントを使用します。つまり、認証が遅くなります。この CNAME レコードが正しく構成されていない場合、たとえば [ **宛先またはポイント先のアドレス**] に入力ミスがある場合、これらのアプリケーションは認証できません。
  
 **ドメインOffice 365 DNS レコードを** 管理する場合は、Office 365 CNAME レコードをセットアップします。 
  
 **DNS ホストでドメイン** の DNS レコードを管理している場合は、DNS ホストの指示に従って、このレコード [を自分で作成します](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。
  
Office 365 展開を計画している場合に、追加または更新が必要なすべての DNS レコードの詳細については、「リファレンス: Office 365 の外部ドメイン ネーム システム[レコード」を参照してください](../../enterprise/external-domain-name-system-records.md)。
