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
description: このOffice 365、一部の暗号化機能は既定で有効になっています。その他の機能は、特定のコンプライアンスまたは法的要件を満たするように構成できます。
ms.openlocfilehash: 84ba80c38d6167fbd9d32fdac0288fa1ef4ac3db
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63680412"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Office 365 Enterprise で暗号化を設定する

暗号化を使用すると、承認されていないユーザーがコンテンツを読み取るのを防いできます。 さまざまな[テクノロジOffice 365](encryption.md)を使用して暗号化を行えるので、暗号化を有効または設定する場所は 1 つで済む必要があります。 この記事では、情報保護戦略の一環として暗号化を設定または構成するさまざまな方法について情報を提供します。

> [!TIP]
> 暗号化に関する技術的な詳細については、「暗号化に関するテクニカル リファレンスの詳細」を参照[Office 365。](technical-reference-details-about-encryption.md)

このOffice 365では、既定でいくつかの暗号化機能を使用できます。 追加の暗号化機能は、特定のコンプライアンスまたは法的要件を満たして構成できます。 次の表では、さまざまなシナリオで使用できるいくつかの暗号化方法について説明します。

<br>

****

|シナリオ|暗号化方法|
|---|---|
|ファイルはコンピューターにWindowsされます|コンピューター レベルでの暗号化は、デバイス上の BitLocker をWindowsできます。 エンタープライズ管理者または IT 管理者Pro、Microsoft Deployment Toolkit (MDT) を使用して設定できます。 「 [BitLocker 用 MDT のセットアップ」を参照してください](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker)。|
|ファイルはモバイル デバイスに保存されます|一部の種類のモバイル デバイスは、既定でそれらのデバイスに保存されるファイルを暗号化します。 組[み込み](https://support.microsoft.com/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)デバイスの機能Mobile Device Management for Office 365、モバイル デバイスがデータにアクセスできるかどうかを決定するポリシーを設定Office 365。 たとえば、コンテンツを暗号化するデバイスだけがデータにアクセスできるポリシー Office 365できます。 「 [デバイス セキュリティ ポリシーの作成と展開」を参照してください](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)。 <p> モバイル デバイスがモバイル デバイスと通信する方法をOffice 365、モバイル デバイスの追加を[検討Microsoft Intune](/mem/intune/fundamentals/setup-steps)。|
|Microsoft のデータ センターでデータを暗号化するために使用する暗号化キーを制御する必要があります|管理者はOffice 365組織の暗号化キーを制御し、それらを使用して Microsoft のデータ センターで保存されているデータを暗号化する Office 365 を構成できます。 <p> [Office 365 のカスタマー キーによるサービスの暗号化](customer-key-overview.md)|
|ユーザーが電子メールで通信している (Exchange Online)|管理者としてExchange Online、電子メールの暗号化を構成するためのいくつかのオプションがあります。 これには、次のものが含まれます。 <ul><li>Azure [Rights Management (](set-up-new-message-encryption-capabilities.md)Azure RMS) Office 365メッセージ暗号化 (OME) を使用して、組織の内部または外部で暗号化されたメッセージを送信できます。</li><li>[S/MIME を使用](/exchange/security-and-compliance/smime-exo/smime-exo)した電子メール メッセージの暗号化とデジタル署名</li><li>TLS を使用 [して別の組織とのメール フローをセキュリティで保護するためのコネクタを設定する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)</li></ul> <p> 「[メールの暗号化」を参照Office 365](./email-encryption.md)。|
|チーム サイトまたはドキュメント ライブラリからファイルにアクセスする (OneDrive for Businessまたは SharePoint Online)|ユーザーがオンラインまたはオンラインに保存OneDrive for BusinessをSharePoint場合、TLS 接続が使用されます。 これは、自動的にOffice 365されます。 「[オンラインおよびオンラインでのデータOneDrive for Business暗号化」をSharePointしてください](./data-encryption-in-odb-and-spo.md)。|
|ファイルは、オンライン会議と IM 会話で共有されます (Skype for Business オンライン)|ユーザーがオンラインでファイルを操作Skype for Business、接続に TLS が使用されます。 これは、自動的にOffice 365されます。 「[セキュリティとアーカイブ (Skype for Business)」を参照してください](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)。|
|ファイルは、オンライン会議と IM 会話で共有されます (Microsoft Teams)|ユーザーがファイルを使用してファイルを操作Microsoft Teams、接続に TLS が使用されます。 これは、自動的にOffice 365されます。 Microsoft Teams現在、暗号化された電子メールのインライン レンダリングはサポートされていません。 暗号化されたメールが暗号化されたメールにMicrosoft Teams、メッセージの暗号化に関する [FAQ を参照してください](./ome-faq.yml#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail-)。|
|

## <a name="additional-information"></a>ページの先頭へ

暗号化オプションを含むファイル保護ソリューションの詳細については、「[File Protection Solutions in Office 365」を参照してください](https://www.microsoft.com/download/details.aspx?id=55523)。
