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
description: 365 Officeでは、一部の暗号化機能は既定で有効になっています。その他の機能は、特定のコンプライアンスまたは法的要件を満たするように構成できます。
ms.openlocfilehash: e153c1e322adaea000cf686e857387d671b18a28
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051679"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Office 365 Enterprise で暗号化を設定する

暗号化を使用すると、承認されていないユーザーがコンテンツを読み取るのを防いできます。 Office [365](encryption.md) の暗号化は、さまざまなテクノロジや方法を使用して行えるので、暗号化を有効または設定する場所は 1 つも使用しません。 この記事では、情報保護戦略の一環として暗号化を設定または構成するさまざまな方法について情報を提供します。
  
> [!TIP]
> 暗号化に関する技術的な詳細をお探しの場合は [、「365」](technical-reference-details-about-encryption.md)の「暗号化に関するテクニカル リファレンスOffice参照してください。
  
365 Officeでは、既定でいくつかの暗号化機能を使用できます。 追加の暗号化機能は、特定のコンプライアンスまたは法的要件を満たして構成できます。 次の表では、さまざまなシナリオで使用できるいくつかの暗号化方法について説明します。
  
|**シナリオ**|**暗号化方法**|
|:-----|:-----|
|ファイルは Windows コンピューターに保存されます  <br/> |コンピューター レベルでの暗号化は、Windows デバイス上の BitLocker を使用して実行できます。 エンタープライズ管理者または IT Pro として、Microsoft Deployment Toolkit (MDT) を使用して設定できます。 [「BitLocker 用 MDT のセットアップ」を参照してください](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker)。  <br/> |
|ファイルはモバイル デバイスに保存されます  <br/> |一部の種類のモバイル デバイスは、既定でそれらのデバイスに保存されるファイルを暗号化します。 [Office 365](https://support.microsoft.com/en-us/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)の組み込みのモバイル デバイス管理の機能を使用すると、モバイル デバイスが Office 365 でデータにアクセスできるかどうかを決定するポリシーを設定できます。 たとえば、コンテンツを暗号化するデバイスだけが 365 データにアクセスOffice設定できます。 「 [デバイス セキュリティ ポリシーの作成と展開」を参照してください](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)。  <br/> モバイル デバイスが 365 を操作する方法をOfficeするには、Microsoft Intune の追加 [を検討してください](/mem/intune/fundamentals/setup-steps)。  <br/> |
|Microsoft のデータ センターでデータを暗号化するために使用する暗号化キーを制御する必要があります  <br/> | Office 365 管理者は、組織の暗号化キーを制御し、それらを使用して Microsoft のデータ センターで保存されているデータを暗号化する Office 365 を構成できます。  <br/> [Office 365 のカスタマー キーによるサービスの暗号化](customer-key-overview.md) <br/> |
|ユーザーが電子メールで通信している (Exchange Online)  <br/> | Exchange Online 管理者は、電子メールの暗号化を構成するためのいくつかのオプションがあります。 これには、次のものが含まれます。  <br/>  Azure Rights Management [(Azure RMS) Office 365 メッセージ暗号化 (OME)](set-up-new-message-encryption-capabilities.md) を使用して、組織の内部または外部で暗号化されたメッセージを送信するユーザーを有効にする  <br/>  [S/MIME を使用したメッセージ署名と暗号化による](../security/defender-365-security/s-mime-for-message-signing-and-encryption.md)電子メール メッセージの暗号化とデジタル署名  <br/>  TLS を使用 [して別の組織とのメール フローをセキュリティで保護するためのコネクタを設定する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) <br/>  「 [メールの暗号化」Office 365 を参照してください](./email-encryption.md)。  <br/> |
|チーム サイトまたはドキュメント ライブラリからファイルにアクセスする (OneDrive for Business または SharePoint Online)  <br/> |ユーザーが OneDrive for Business または SharePoint Online に保存されたファイルを操作している場合、TLS 接続が使用されます。 これは、365 Officeに組み込まれる。 [「OneDrive for Business および SharePoint Online でのデータ暗号化」を参照してください](./data-encryption-in-odb-and-spo.md)。  <br/> |
|ファイルは、オンライン会議と IM 会話で共有されます (Skype for Business Online)  <br/> |ユーザーが Skype for Business Online を使用してファイルを操作している場合、接続には TLS が使用されます。 これは、365 Officeに組み込まれる。 「 [セキュリティとアーカイブ (Skype for Business Online)」を参照してください](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)。  <br/> |
|ファイルは、オンライン会議と IM 会話で共有されます (Microsoft Teams)  <br/> |ユーザーが Microsoft Teams を使用してファイルを操作している場合、接続には TLS が使用されます。 これは、365 Officeに組み込まれる。 Microsoft Teams は現在、暗号化された電子メールのインライン レンダリングをサポートしません。 暗号化されたメールが暗号化されたとして Microsoft Teams に届かされるのを防ぐには、「メッセージの暗号化に関する [よく寄せられる質問」を参照してください](./ome-faq.md?view=o365-worldwide#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail)。  <br/> 

## <a name="additional-information"></a>追加情報

暗号化オプションを含むファイル保護ソリューションの詳細については [、「File Protection Solutions in Office 365」を参照してください](https://www.microsoft.com/download/details.aspx?id=55523)。
