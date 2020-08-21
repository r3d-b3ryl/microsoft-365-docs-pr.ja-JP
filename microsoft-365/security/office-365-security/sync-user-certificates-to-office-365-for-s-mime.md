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
description: この記事では、Exchange Online で S/MIME 保護メッセージを送信する前に Office 365 に適切な証明書を公開する方法について説明します。
ms.openlocfilehash: 634b65e45b01186a27f9ae61c91d4b27f1a11635
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826483"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>S/MIME 用にユーザー証明書を Office 365 に同期する

Exchange Online で S/MIME 保護されたメッセージを送信するには、適切な証明書をセットアップする必要があります。 暗号化されたメッセージを Exchange Online 経由で送信するために、送信者の電子メール アプリでは受信者の公開証明書を使用してメッセージを暗号化します。 この公開 X.509 証明書を Office 365 に公開する必要があります。

## <a name="to-sync-certificates-that-support-smime"></a>S/MIME をサポートする証明書を同期するには

証明書を発行して、ローカルの Active Directory ドメイン サービスで公開することによって、S/MIME のセットアップを開始します。 詳細については、「[Active Directory 証明書サービスの概要](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))」を参照してください。

証明書が公開されたら、Azure AD Connect ツールを使用してオンプレミスの Exchange 環境からユーザー データを Office 365 に同期します。 このプロセスの詳細については、「Azure の同期 [」を参照AD「同期を理解してカスタマイズする」を参照してください](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)。

S/MIME のために他のディレクトリ データを同期する場合に、このツールは、各ユーザー オブジェクトの  **userCertificate** 属性と **userSMIMECertificate** 属性を同期して、そのデータをメッセージの署名と暗号化に使用できるようにします。

## <a name="more-information"></a>詳細情報

[S/MIME によるメッセージの署名と暗号化](s-mime-for-message-signing-and-encryption.md)

[Azure AD Connect とは?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
