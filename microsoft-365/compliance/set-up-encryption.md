---
title: Office 365 Enterprise で暗号化を設定する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: このOffice 365、一部の暗号化機能は既定で有効になっています。その他の機能は、特定のコンプライアンスまたは法的要件を満たするように構成できます。
ms.openlocfilehash: a9a3170fdb99a4acfec8cf4d3b03ab9b584197bd
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216384"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Office 365 Enterprise で暗号化を設定する

暗号化を使用すると、承認されていないユーザーがコンテンツを読み取るのを防いできます。 さまざまなテクノロジ[Office 365](encryption.md)を使用して暗号化を行えるので、暗号化を有効または設定する場所は 1 つも使用しません。 この記事では、情報保護戦略の一環として暗号化を設定または構成するさまざまな方法について情報を提供します。

> [!TIP]
> 暗号化に関する技術的な詳細をお探しの場合は、「暗号化に関するテクニカル[リファレンス](technical-reference-details-about-encryption.md)の詳細」を参照Office 365。

このOffice 365では、既定でいくつかの暗号化機能を使用できます。 追加の暗号化機能は、特定のコンプライアンスまたは法的要件を満たして構成できます。 次の表では、さまざまなシナリオで使用できるいくつかの暗号化方法について説明します。

<br>

****

|シナリオ|暗号化方法|
|---|---|
|ファイルはコンピューターにWindowsされます|コンピューター レベルでの暗号化は、デバイス上の BitLocker をWindowsできます。 エンタープライズ管理者または IT 管理者Pro、Microsoft Deployment Toolkit (MDT) を使用して設定できます。 [「BitLocker 用 MDT のセットアップ」を参照してください](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker)。|
|ファイルはモバイル デバイスに保存されます|一部の種類のモバイル デバイスは、既定でそれらのデバイスに保存されるファイルを暗号化します。 組[み込み](https://support.microsoft.com/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)アプリケーションの機能Mobile Device Management for Office 365、モバイル デバイスがデータにアクセスできるかどうかを決定するポリシーを設定Office 365。 たとえば、コンテンツを暗号化するデバイスだけがデータにアクセスできるポリシー Office 365できます。 「 [デバイス セキュリティ ポリシーの作成と展開」を参照してください](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)。 <p> モバイル デバイスがモバイル デバイスと通信する方法を詳細に制御Office 365、モバイル デバイスの追加を[検討Microsoft Intune。](/mem/intune/fundamentals/setup-steps)|
|Microsoft のデータ センターでデータを暗号化するために使用する暗号化キーを制御する必要があります|管理者はOffice 365組織の暗号化キーを制御し、それらを使用して Microsoft のデータ センターで保存されているデータを暗号化する Office 365 を構成できます。 <p> [Office 365 のカスタマー キーによるサービスの暗号化](customer-key-overview.md)|
|ユーザーが電子メールで通信している (Exchange Online)|管理者としてExchange Online、電子メールの暗号化を構成するためのいくつかのオプションがあります。 たとえば、次の環境です。: <ul><li>Azure Rights Management (Azure RMS) Office 365メッセージ暗号化[(OME)](set-up-new-message-encryption-capabilities.md)を使用して、組織の内部または外部で暗号化されたメッセージを送信できます。</li><li>[S/MIME を使用](/exchange/security-and-compliance/smime-exo/smime-exo)した電子メール メッセージの暗号化とデジタル署名</li><li>TLS を使用 [して別の組織とのメール フローをセキュリティで保護するためのコネクタを設定する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)</li></ul> <p> 「[メールの暗号化」を参照Office 365。](./email-encryption.md)|
|チーム サイトまたはドキュメント ライブラリからファイルにアクセスする (OneDrive for Businessまたは SharePoint Online)|ユーザーがオンラインまたはオンラインに保存されたOneDrive for Business操作SharePoint TLS 接続が使用されます。 これは、自動的にOffice 365されます。 「[データ暗号化」および「OneDrive for BusinessオンラインSharePoint」を参照してください](./data-encryption-in-odb-and-spo.md)。|
|ファイルは、オンライン会議と IM 会話で共有されます (Skype for Business オンライン)|ユーザーがオンラインでファイルを操作Skype for Business、TLS が接続に使用されます。 これは、自動的にOffice 365されます。 「Security [and Archiving (Skype for Business Online)」を参照してください](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)。|
|ファイルは、オンライン会議と IM 会話で共有されます (Microsoft Teams)|ユーザーがファイルを使用してファイルを操作Microsoft Teams、接続に TLS が使用されます。 これは、自動的にOffice 365されます。 Microsoft Teams現在、暗号化された電子メールのインライン レンダリングはサポートされていません。 暗号化されたメールが暗号化されたメールにMicrosoft Teamsメッセージ暗号化に関する FAQ を[参照してください](./ome-faq.yml#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail-)。|
|

## <a name="additional-information"></a>ページの先頭へ

暗号化オプションを含むファイル保護ソリューションの詳細については[、「File Protection Solutions in Office 365」を参照してください](https://www.microsoft.com/download/details.aspx?id=55523)。
