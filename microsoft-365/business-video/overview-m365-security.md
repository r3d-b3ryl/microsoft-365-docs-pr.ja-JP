---
title: Microsoft 365 Business Premium Security の概要
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
description: ビジネス向け Microsoft 365 に含まれるセキュリティ機能について説明します。
ms.openlocfilehash: c0890f097177848ef5a75c7c139c7dbc69e4eba1
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007095"
---
# <a name="overview-of-security"></a>セキュリティの概要

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mzxI?autoplay=false]

Microsoft 365 Business Premium には、脅威保護、データ保護、デバイス管理機能が備わっています。

|![脅威の保護](../media/m365-business-security-threat-protection.png)<br/>[脅威の保護](#threat-protection)|![クライアントとの共同作業](../media/m365-business-security-data-protection.png) <br/>[データ保護](#data-protection) | ![デバイスの管理](../media/m365-business-security-device-management.png) <br/>[デバイスの管理](#device-management) |
|--|--|--|

## <a name="threat-protection"></a>脅威に対する保護

Microsoft 365 Business Premium には [、Office 365 Advanced Threat Protection (ATP)](safe-links.md)、マルウェア、ランサムウェア、有害なリンクなどからユーザーを保護するクラウドベースの電子メール フィルター サービスが含まれています。 ATP セーフ リンクは、電子メールまたはドキュメント内の悪意のある URL からOfficeします。 ATP の安全な添付ファイルは、メッセージやドキュメントに添付されているマルウェアやウイルスから保護します。

[多要素認証 (MFA) 、](turn-on-mfa.md)または 2 段階認証では、リソースにアクセスする前に、ID を確認するために、検証コードなどの 2 つ目の認証形式を提示する必要があります。

[Windows Defender、](/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10) ウイルス、マルウェア、スパイウェア、その他の脅威から、システム、ファイル、およびオンライン アクティビティに対する包括的な保護を提供します。

## <a name="data-protection"></a>データの保護

Microsoft 365 Business Premium のデータ保護機能は、重要なデータが安全に保護され、承認されたユーザーのみがアクセスできます。

データ損失防止 [(DLP)](set-up-dlp.md) ポリシーを使用して、社会保障番号やクレジット カード番号などの機密情報を識別して管理し、誤って共有しきれなくすることができます。

[Office 365 Message Encryption](/microsoft-365/compliance/ome) は、暗号化機能とアクセス権機能を組み合わせ、目的の受信者だけがメッセージ コンテンツを表示できるよう支援します。 Office 365 Message Encryption は、Outlook.com Yahoo!、Gmail、その他のメール サービスと連携します。

[Exchange Online Archiving](/office365/servicedescriptions/exchange-online-archiving-service-description/exchange-online-archiving-service-description) は、Microsoft Exchange または Exchange Online と組み合わせ、保留やデータの冗長性などの高度なアーカイブ機能を提供するクラウドベースのアーカイブ ソリューションです。 保持ポリシーを使用すると、組織が電子メールや他の通信に関連する負債を減らすのに役立ちます。 会社が訴訟に関連する通信を保持する必要がある場合は、In-Place保持と訴訟ホールドを使用して、関連する電子メールを保持できます。

## <a name="device-management"></a>デバイスの管理

Microsoft 365 Business Premium の高度なデバイス管理機能を使用すると、登録されたデバイスでユーザーが実行できる操作を監視および制御できます。 これらの機能には、条件付きアクセス、 [モバイル デバイス管理 (MDM)、BitLocker、](/microsoft-365/admin/basic-mobility-security/manage-enrolled-devices)自動更新が含まれます。

条件付きアクセス ポリシーを使用して、特定のユーザーとタスクに対して追加のセキュリティ対策を要求できます。 たとえば、多要素認証 [(MFA) を](/microsoft-365/business-video/turn-on-mfa) 要求したり、条件付きアクセスをサポートしないクライアントをブロックすることができます。

MDM を使用すると、iPhone、iPad、Android、Windows 電話など、ユーザーのモバイル デバイスのセキュリティ保護と管理に役立ちます。 デバイス セキュリティ ポリシーを作成および管理し、デバイスをリモートでワイプしてすべての会社データを削除し、デバイスを出荷時設定にリセットし、詳細なデバイス レポートを表示できます。

BitLocker 暗号化を有効にして、デバイスが紛失または盗まれた場合にデータを保護し、Windows Exploit Guard がランサムウェアに対する高度な保護を提供できます。

自動更新を構成して、最新のセキュリティ機能と更新プログラムがすべてのユーザー デバイスに適用されます。

## <a name="recommended-security-guidance"></a>推奨されるセキュリティ ガイダンス

Microsoft Business Premium を使用している場合、以下のライブラリのガイダンスに従うと、最も手早くセキュリティ設定を行い安全に共同作業ができるでしょう: [中小企業向け Microsoft 365 およびキャンペーン ](../campaigns/index.md)。 このガイダンスは、Microsoft Defending Democracy チームと協力して開発され、高度なハッカーによるサイバー攻撃から中小企業のユーザーを保護します。
