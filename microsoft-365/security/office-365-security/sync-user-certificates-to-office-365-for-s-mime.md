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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: この記事では、Exchange Online で S/MIME で保護されたメッセージを送信する前に、Office 365 に適切な証明書を発行する方法について学習します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 387f9f405afd45254c6568aa92334a7ee5b4171f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916456"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>S/MIME 用にユーザー証明書を Office 365 に同期する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online で S/MIME で保護されたメッセージを送信するには、その前に適切な証明書を設定する必要があります。 Exchange Online を介して暗号化されたメッセージを送信するために、送信者の電子メール アプリは受信者の公開証明書を使用してメッセージを暗号化します。 この公開 X.509 証明書を Office 365 に公開する必要があります。

## <a name="to-sync-certificates-that-support-smime"></a>S/MIME をサポートする証明書を同期するには

証明書を発行して、ローカルの Active Directory ドメイン サービスで公開することによって、S/MIME のセットアップを開始します。 詳細については、「[Active Directory 証明書サービスの概要](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))」を参照してください。

証明書を発行した後、Azure AD Connect ツールを使用して、オンプレミスの Exchange 環境から 365 にユーザー データをOfficeします。 このプロセスの詳細については、「Azure AD 接続同期: 同期の理解と [カスタマイズ」を参照してください](/azure/active-directory/hybrid/how-to-connect-sync-whatis)。

他のディレクトリ データの同期と共に、S/MIME の目的で、このツールはユーザー オブジェクトごとに  **userCertificate** 属性と **userSMIMECertificate** 属性を同期し、データを使用してメッセージの署名と暗号化を行います。

## <a name="more-information"></a>詳細情報

[S/MIME によるメッセージの署名と暗号化](s-mime-for-message-signing-and-encryption.md)

[Azure AD Connect とは?](/azure/active-directory/hybrid/whatis-azure-ad-connect)