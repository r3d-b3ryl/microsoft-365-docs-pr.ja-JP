---
title: S/MIME 用にユーザー証明書を Office 365 に同期させる
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: この記事では、S/MIME で保護されたメッセージを Exchange Online で送信する前に、Office 365 に適切な証明書を発行する方法について説明します。
ms.openlocfilehash: 3551dbacc3cc6279d319860f1133d059216ae591
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202105"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>S/MIME 用にユーザー証明書を Office 365 に同期する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


すべてのユーザーが S/MIME で保護されたメッセージを Exchange Online で送信できるようにするには、適切な証明書をセットアップする必要があります。 Exchange Online を介して暗号化されたメッセージを送信する場合、送信者の電子メールアプリは受信者のパブリック証明書を使用してメッセージを暗号化します。 この公開 X.509 証明書を Office 365 に公開する必要があります。

## <a name="to-sync-certificates-that-support-smime"></a>S/MIME をサポートする証明書を同期するには

証明書を発行して、ローカルの Active Directory ドメイン サービスで公開することによって、S/MIME のセットアップを開始します。 詳細については、「[Active Directory 証明書サービスの概要](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))」を参照してください。

証明書が公開されたら、Azure AD Connect ツールを使用してオンプレミスの Exchange 環境から Office 365 にユーザーデータを同期します。 このプロセスの詳細については、「 [AZURE AD Connect sync: 同期の理解とカスタマイズ](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)」を参照してください。

S/MIME 用に他のディレクトリデータを同期することに加えて、ツールは各ユーザーオブジェクトの  **Usercertificate** 属性と **userSMIMECertificate** 属性を同期し、データを使用してメッセージの署名と暗号化を行うことができるようにします。

## <a name="more-information"></a>詳細情報

[S/MIME によるメッセージの署名と暗号化](s-mime-for-message-signing-and-encryption.md)

[Azure AD Connect とは?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
