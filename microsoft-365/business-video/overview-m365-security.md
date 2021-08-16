---
title: セキュリティのMicrosoft 365 Business Premium概要
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: ビジネス向けサービスに含まれるセキュリティMicrosoft 365を確認します。
ms.openlocfilehash: 3c5348eb268373ff11b7e926f39d385451a4b2760978029484a2116885c7e9ea
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53887778"
---
# <a name="overview-of-security"></a>セキュリティの概要

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mzxI?autoplay=false]

Microsoft 365 Business Premiumは、脅威保護、データ保護、デバイス管理機能を提供し、オンラインの脅威や不正アクセスから企業を保護し、携帯電話、タブレット、およびコンピューター上の企業データを保護および管理するのに役立ちます。

|![脅威の保護](../media/m365-business-security-threat-protection.png)<br/>[脅威の保護](#threat-protection)|![クライアントとの共同作業](../media/m365-business-security-data-protection.png) <br/>[データ保護](#data-protection) | ![デバイスの管理](../media/m365-business-security-device-management.png) <br/>[デバイスの管理](#device-management) |
|--|--|--|

## <a name="threat-protection"></a>脅威に対する保護

Microsoft 365 Business Premium高度[Office 365保護 (ATP)、](safe-links.md)マルウェア、ランサムウェア、有害なリンクなどからユーザーを保護するクラウドベースの電子メール フィルター サービスが含まれます。 ATP セーフ リンクは、電子メールまたはドキュメント内の悪意のある URL からOfficeします。 ATP セーフ添付ファイルは、メッセージやドキュメントに添付されているマルウェアやウイルスから保護します。

[多要素認証 (MFA) 、](turn-on-mfa.md)または 2 段階認証では、リソースにアクセスする前に、ID を確認するために、検証コードなどの 2 つ目の認証形式を提示する必要があります。

[Windows Defender、](/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10)ウイルス、マルウェア、スパイウェア、その他の脅威から、システム、ファイル、およびオンライン アクティビティに対する包括的な保護を提供します。

## <a name="data-protection"></a>データの保護

データ保護機能は、Microsoft 365 Business Premiumデータが安全に保管され、承認されたユーザーのみがデータにアクセスできるのを防ごうのに役立ちます。

データ損失防止 [(DLP)](set-up-dlp.md) ポリシーを使用して、社会保障番号やクレジット カード番号などの機密情報を識別して管理し、誤って共有しきれなくすることができます。

[Office 365 Message Encryption](/microsoft-365/compliance/ome)アクセス権機能を組み合わせ、目的の受信者だけがメッセージ コンテンツを表示できるよう支援します。 Office 365 Message Encryption Outlook.com、Yahoo!、Gmail、その他のメール サービスで動作します。

[Exchange Online Archiving](/office365/servicedescriptions/exchange-online-archiving-service-description/exchange-online-archiving-service-description)は、Microsoft Exchange または Exchange Online と組み合わせ、保留やデータの冗長性などの高度なアーカイブ機能を提供するクラウドベースのアーカイブ ソリューションです。 保持ポリシーを使用すると、組織が電子メールや他の通信に関連する負債を減らすのに役立ちます。 会社が訴訟に関連する通信を保持する必要がある場合は、In-Place保持と訴訟ホールドを使用して、関連する電子メールを保持できます。

## <a name="device-management"></a>デバイスの管理

Microsoft 365 Business Premium高度なデバイス管理機能を使用すると、登録済みのデバイスでユーザーが実行できる操作を監視および制御できます。 これらの機能には、条件付きアクセス、 [モバイル デバイス管理 (MDM)、BitLocker、](/microsoft-365/admin/basic-mobility-security/manage-enrolled-devices)自動更新が含まれます。

条件付きアクセス ポリシーを使用して、特定のユーザーとタスクに対して追加のセキュリティ対策を要求できます。 たとえば、多要素認証 [(MFA) を](/microsoft-365/business-video/turn-on-mfa) 要求したり、条件付きアクセスをサポートしないクライアントをブロックすることができます。

MDM を使用すると、ユーザーのモバイル デバイス (iPhone、iPad、Android、携帯電話など) のセキュリティ保護と管理Windowsできます。 デバイス セキュリティ ポリシーを作成および管理し、デバイスをリモートでワイプしてすべての会社データを削除し、デバイスを出荷時設定にリセットし、詳細なデバイス レポートを表示できます。

BitLocker 暗号化を有効にして、デバイスが紛失または盗難に備えデータを保護し、Windows Exploit Guard を有効にしてランサムウェアに対する高度な保護を提供できます。

自動更新を構成して、最新のセキュリティ機能と更新プログラムがすべてのユーザー デバイスに適用されます。

## <a name="recommended-security-guidance"></a>推奨されるセキュリティ ガイダンス

Microsoft Business Premium を使用している場合、以下のライブラリのガイダンスに従うと、最も手早くセキュリティ設定を行い安全に共同作業ができるでしょう: [中小企業向け Microsoft 365 およびキャンペーン ](../campaigns/index.md)。 このガイダンスは、Microsoft Defending Democracy チームと協力して開発され、高度なハッカーによるサイバー攻撃から中小企業のユーザーを保護します。
