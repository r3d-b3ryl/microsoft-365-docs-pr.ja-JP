---
title: Office 365 Enterprise で暗号化を設定する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: landing-page
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: Office 365では、一部の暗号化機能が既定で有効になります。他の機能は、特定のコンプライアンスまたは法的要件を満たすように構成できます。
ms.openlocfilehash: 86e39603025c29d47a2e1b2b5b946bfe2549245d
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66622109"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Office 365 Enterprise で暗号化を設定する

暗号化を使用すると、承認されていないユーザーがコンテンツを読み取られるのを防ぎます。 [Office 365の暗号化](encryption.md)はさまざまなテクノロジと方法を使用して行うことができるため、暗号化を有効または設定する場所は 1 つではありません。 この記事では、情報保護戦略の一環として暗号化を設定または構成するさまざまな方法について説明します。

> [!TIP]
> 暗号化に関する技術的な詳細については、「[Office 365での暗号化に関する技術リファレンスの詳細](technical-reference-details-about-encryption.md)」を参照してください。

Office 365では、既定ではいくつかの暗号化機能を使用できます。 特定のコンプライアンスまたは法的要件を満たすように、追加の暗号化機能を構成できます。 次の表では、さまざまなシナリオに対するいくつかの暗号化方法について説明します。

<br>

****

|シナリオ|暗号化メソッド|
|---|---|
|ファイルは Windows コンピューターに保存されます|コンピューター レベルでの暗号化は、Windows デバイスの BitLocker を使用して行うことができます。 エンタープライズ管理者または IT Pro として、Microsoft Deployment Toolkit (MDT) を使用してこれを設定できます。 [BitLocker の MDT のセットアップに関するページを](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker)参照してください。|
|ファイルはモバイル デバイスに保存されます|一部の種類のモバイル デバイスでは、既定でそれらのデバイスに保存されているファイルが暗号化されます。 [組み込みのMobile Device Management for Office 365の機能](https://support.microsoft.com/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)を使用すると、モバイル デバイスがOffice 365内のデータにアクセスできるかどうかを決定するポリシーを設定できます。 たとえば、コンテンツを暗号化するデバイスのみがOffice 365データにアクセスできるようにするポリシーを設定できます。 [デバイス セキュリティ ポリシーの作成と展開に関する説明を](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)参照してください。 <p> モバイル デバイスとOffice 365の対話方法をさらに制御するには、[Microsoft Intune](/mem/intune/fundamentals/setup-steps)の追加を検討してください。|
|Microsoft のデータ センターでデータを暗号化するために使用される暗号化キーを制御する必要があります|Office 365管理者は、組織の暗号化キーを制御し、それらを使用して Microsoft のデータ センターで保存データを暗号化するようにOffice 365を構成できます。 <p> [Microsoft Purview カスタマー キーを使用したサービスの暗号化](customer-key-overview.md)|
|ユーザーがメール経由で通信している (Exchange Online)|Exchange Online管理者は、電子メール暗号化を構成するためのいくつかのオプションがあります。 たとえば、次の環境です。: <ul><li>[Office 365 メッセージ暗号化 (OME)](set-up-new-message-encryption-capabilities.md) と Azure Rights Management (Azure RMS) を使用して、ユーザーが組織内または外部で暗号化されたメッセージを送信できるようにする</li><li>[S/MIME を](/exchange/security-and-compliance/smime-exo/smime-exo)使用した電子メール メッセージの暗号化とデジタル署名</li><li>TLS を使用して[別の組織とセキュリティで保護されたメール フロー用のコネクタを設定](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)する</li></ul> <p> [Office 365の電子メール暗号化に関するOffice 365](./email-encryption.md)を参照してください。|
|ファイルは、チーム サイトまたはドキュメント ライブラリ (OneDrive for Business または SharePoint Online) からアクセスされます。|ユーザーがOneDrive for Businessまたは SharePoint Online に保存されたファイルを操作している場合は、TLS 接続が使用されます。 これは自動的にOffice 365に組み込まれています。 [OneDrive for Businessおよび SharePoint Online のデータ暗号化に関する](./data-encryption-in-odb-and-spo.md)サイトを参照してください。|
|ファイルは、オンライン会議と IM 会話で共有されます (オンラインSkype for Business)|ユーザーが Skype for Business Online を使用してファイルを操作している場合、接続には TLS が使用されます。 これは自動的にOffice 365に組み込まれています。 [セキュリティとアーカイブ (オンラインSkype for Business)](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)を参照してください。|
|ファイルは、オンライン会議と IM 会話で共有されます (Microsoft Teams)|ユーザーが Microsoft Teams を使用してファイルを操作している場合は、TLS が接続に使用されます。 これは自動的にOffice 365に組み込まれています。 Microsoft Teams では、現在、暗号化された電子メールのインライン レンダリングはサポートされていません。 暗号化された電子メールが暗号化された状態で Microsoft Teams にアクセスできないようにするには、「 [メッセージ暗号化に関する FAQ」を参照してください](./ome-faq.yml#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail-)。|
|

## <a name="additional-information"></a>その他の情報

暗号化オプションを含むファイル保護ソリューションの詳細については、[Office 365の File Protection ソリューションに関するページを](https://www.microsoft.com/download/details.aspx?id=55523)参照してください。
