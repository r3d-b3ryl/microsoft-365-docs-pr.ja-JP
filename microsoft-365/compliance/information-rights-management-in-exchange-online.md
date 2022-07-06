---
title: AD RMS による Exchange Online のメールの暗号化
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
ms.custom:
- seo-marvel-apr2020
description: 組織の要件を満たすために オンプレミスの Active Directory Rights Management Service (AD RMS) を使用するように Exchange Online IRM を構成する方法について説明します。
ms.openlocfilehash: 926bea0b1f9379d2eaad2bc7c5bd672f98329b8a
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66628795"
---
# <a name="exchange-online-mail-encryption-with-ad-rms"></a>AD RMS による Exchange Online のメールの暗号化

情報漏洩を防止するために、Exchange Online には、電子メール メッセージおよび添付ファイルをオンラインおよびオフラインで保護する Information Rights Management (IRM) 機能が搭載されています。 組織の要件を満たすために、必要に応じて オンプレミスの Active Directory Rights Management Service (AD RMS) を使用するように、Exchange Online IRM を構成できます。 これは一般的ではありません。 AD RMS を使用する要件がない場合は、代わりに[Microsoft Purview Message Encryption](ome.md)を使用します。

IRM 保護は、ユーザーが Microsoft Outlook や Outlook on the web で適用したり、管理者がトランスポート保護ルールや Outlook の保護ルールを使用して適用したりできます。 IRM を使用すると、管理者とユーザーは、電子メールに含まれている機密性の高いデータのアクセス、転送、印刷、コピーをだれに許可するかを管理できるようになります。
  
## <a name="changes-to-how-irm-works-with-message-encryption-and-azure-active-directory"></a>IRM とメッセージの暗号化と Azure Active Directory の動作に関する変更

2017 年 9 月の時点で、組織のMicrosoft Purview Message Encryptionを設定すると、Azure Rights Management (Azure RMS) で使用する IRM も設定されています。 IRM および Azure RMS を別個にセットアップすることはなくなりました。 代わりに、メッセージの暗号化と権限管理がシームレスに連携します。 Microsoft Purview Message Encryptionの詳細については、「[メッセージ暗号化に関する FAQ」を](./ome-faq.yml)参照してください。 組織内でMicrosoft Purview Message Encryptionの使用を開始する準備ができたら、「[Microsoft Purview Message Encryptionのセットアップ](./set-up-new-message-encryption-capabilities.md)」を参照してください。
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>IRM が Exchange Online および Active Directory Rights Management サービスと協働する方法

Exchange Online IRM では、Windows Server 2008 以降の情報保護テクノロジであるオンプレミスの Active Directory Rights Management サービス (AD RMS) が使用されます。IRM 保護を電子メールに適用するには、AD RMS 権利ポリシー テンプレートを電子メール メッセージに適用します。権限はメッセージ自体に添付されているため、オンラインとオフラインの両方、および組織のファイアウォールの内外両方で保護が有効になります。
  
ユーザーは、電子メール メッセージにテンプレートを適用して、メッセージに対する受信者のアクセス許可を制御できます。転送、メッセージからの情報の抽出、メッセージの保存、メッセージの印刷などの操作を制御するには、AD RMS 権利ポリシーをメッセージに適用します。
  
Windows Server 2008 以降を実行している AD RMS サーバーを使用するよう IRM を構成できます。 この AD RMS サーバーは、クラウドベースの組織の AD RMS 権利ポリシー テンプレートを管理するために使用できます。 Outlook では、ユーザーが IRM 保護を送信メッセージに適用できるようにする目的にも AD RMS サーバーが使用されます。 詳細については、「 [オンプレミスの AD RMS サーバーを使用するように IRM を構成する」を参照してください](configure-irm-to-use-an-on-premises-ad-rms-server.md)。
  
有効になっていれば、次のように、IRM 保護をメッセージに適用できます。
  
- **ユーザーが Outlook と Outlook on the web を使用して手動でテンプレートを適用する** ユーザーは、 **[アクセス許可の設定]** リストからテンプレートを選択して、AD RMS 権利ポリシー テンプレートを電子メール メッセージに適用できます。ユーザーが IRM 保護メッセージを送信するときは、サポートされている形式を使用している添付ファイルもメッセージと同じ IRM 保護の対象となります。IRM 保護は、Word、Excel、PowerPoint に関連付けられたファイルだけでなく, .xps ファイルや添付された電子メール メッセージにも適用されます。

- **管理者がトランスポート保護ルールを使用して Outlook と Outlook on the web の両方に IRM 保護を自動的に適用する** 管理者は、メッセージを IRM で保護するためのトランスポート保護ルールを作成できます。ルール条件を満たすメッセージに AD RMS 権利ポリシー テンプレートを適用するように、トランスポート保護ルールの処理を構成します。IRM を有効にすると、 **メッセージに権利保護を適用する** というトランスポート保護ルールの処理で組織の AD RMS 権利ポリシー テンプレートを使用できるようになります。

- **管理者が Outlook 保護ルールを作成する** Outlook 保護ルールは、送信者の部署、メッセージの送信先、受信者が組織内か組織外かなどのメッセージの条件に基づいて、IRM 保護を Outlook 2010 (Outlook on the web ではない) のメッセージに自動的に適用します。詳細については、「 [Create an Outlook Protection Rule](/exchange/create-an-outlook-protection-rule-exchange-2013-help)」を参照してください。
