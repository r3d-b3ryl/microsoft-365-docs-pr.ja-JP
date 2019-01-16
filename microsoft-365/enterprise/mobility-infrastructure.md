---
title: フェーズ 5 - モバイル デバイスの管理
description: Microsoft 365 エンタープライズには、Microsoft Intune を使用してモバイル デバイスの管理が含まれています。要件と前提条件を確認、Intune は、Azure Active Directory リソースを使用して設定、macOS、iOS、Android、および Windows の登録、デバイス、アプリケーションを展開、構成プロファイルを作成、コンプライアンス ・ ポリシーを使用および携帯用の条件付きのアクセスを有効にします。Microsoft 365 エンタープライズ ・ デバイスの管理です。
keywords: Microsoft 365、Microsoft 365 エンタープライズでは、Microsoft 365 マニュアル、モバイル デバイスの管理、Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/18/2018
ms.topic: conceptual
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: 3afc28f0d21918c027a6a1622a40318e333f7ab4
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869656"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>Microsoft 365 エンタープライズのフェーズ 5: モバイル デバイスの管理

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*この機能は Microsoft 365 エンタープライズの E3、E5 のバージョンに適用されます。*

Microsoft 365 エンタープライズには、デバイス、およびそれらのアプリケーションは、組織内での管理に役立つ機能が含まれています。Microsoft Intune を使用すると、iOS、Android、macOS、およびデータを含む、組織のリソースへのアクセスを保護するために Windows デバイスを管理できます。Intune は、Azure Active Directory (Azure AD) と統合 Microsoft 365 の次のビジネス シナリオを有効にします。

- 組織内外でファイルを保存および共有して、組織の境界を越えてシームレスに作業を行います
- 柔軟なワーク スタイルを維持しながら、いつでもどこでもデバイスを使って多くのことを安全に成し遂げることができます
- 業界内で確証された世界標準のコンプライアンスに適合したコントロールと可視性により、安心感を提供します
- 情報を保護して、データ損失のリスクを軽減します
- 検出し、外部の脅威から保護します。
- 監視、レポート、および組織のセキュリティを提供するのには迅速に対応する利用状況を分析
- ユーザーと自分のアカウントを保護します。

詳細については、「[Microsoft 365 を使用したデジタル改革](http://transform.microsoft.com)」を参照してください。 

このフェーズでは、作成し、セキュリティで保護され、データを保つためにポリシーを適用する Intune で、デバイスを登録します。Intune ドキュメントの全体のライブラリは、[利用可能なオンライン](https://docs.microsoft.com/intune)です。開始する前に[Intune 展開の計画、設計および実装ガイド](https://docs.microsoft.com/intune/planning-guide)を確認することをお勧めします。

## <a name="step-1-plan-for-your-scenario"></a>シナリオでは、手順 1: 計画

モバイル デバイスを管理する主な理由の 1 つは、セキュリティで保護し、組織のリソースを保護するためにです。[Microsoft Intune を使用する一般的な方法](https://docs.microsoft.com/intune/common-scenarios)では、実際の例については、Office 365 の電子メールおよびデータのセキュリティ設定が一覧表示されます。

Intune では、[モバイル デバイス管理 (MDM) やモバイル アプリケーションの管理 (MAM)](https://docs.microsoft.com/intune/byod-technology-decisions)を使用して、組織へのアクセスを管理するためのオプションを示します。MDM は、ユーザーは Intune では、そのデバイスを「登録」とします。登録、管理対象デバイスであり、ポリシー、規則、および組織で使用される設定を受け取ることができます。などの具体的なアプリケーションのインストールのパスワード ポリシーを作成、VPN 接続をインストールできます。

自分個人のデバイスを持つユーザーすることがない、デバイスを登録または Intune のポリシーを管理します。組織のリソースとデータを保護する必要があります。このシナリオでは、MAM を使用して、アプリケーションを保護できます。たとえば、SharePoint をデバイスにアクセスするときに PIN を入力するユーザーを必要とする MAM ポリシーを使用できます。

どのようにしようとしている個人または組織が所有するデバイスを管理するかを決定します。使用によって、異なるデバイスを処理することができます。などの可能性がありますさまざまなプラン ユーザーに必要な人事 (HR) または販売のユーザーにします。[モバイル デバイス管理のユース ケース シナリオを識別](https://docs.microsoft.com/intune/planning-guide-scenarios)できますねと、さまざまなシナリオをいくつかのガイダンスが含まれます。

## <a name="step-2-get-your-prerequisites"></a>手順 2: 前提条件を取得します。

次に、前提条件がお客様の要件に基づいて、および前の手順で作成した独自のシナリオを取得します。[実装計画に](https://docs.microsoft.com/intune/planning-guide-onboarding)は、すべての要件を示します。Intune Microsoft 365 との必要な重要な項目を以下に示します。

- **Intune サブスクリプション**: Microsoft 365、 [Azure ポータル](https://portal.azure.com)の Microsoft Intune にアクセスすることに含まれています。
- **Office 365 サブスクリプション**: Microsoft 365 に含まれているし、メールを含む、Office アプリケーションの使用
- **Azure Active Directory (AD) プレミアム**: Microsoft 365 では、含まれており、ユーザーまたはセキュリティ グループを作成するために使用します。これらのグループを作成したら、Intune ポリシーを受信するデバイスのロックを解除するパスワードの長さを強制することなどです。作成するグループ[フェーズ 2: アイデンティティ](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)使用することができます。

組織のニーズに応じて、いくつかの追加要件がある可能性があります。たとえば、iOS のデバイスを管理すること、Apple MDM のプッシュの証明書が必要があります。使用する場合、オンプレミスの Exchange、オンプレミスの Exchange コネクタを必要があります。これらの手順を表示するときにこれらの要件の概要です。

## <a name="step-3-set-up-intune"></a>Intune セットアップの手順 3:

Intune では、Azure AD、ドメイン、ユーザー、グループなどの多くの機能を使用します。企業のニーズに合わせて新しいユーザーや新しいグループを作成することもできます。たとえば、 **iOS デバイス**、または**人事部のすべてのユーザー**と呼ばれるグループを作成できます。 単純または高度なルールに基づいてデバイス ・ グループまたはユーザーのいずれかを作成できる[動的なグループ](https://docs.microsoft.com/intune/groups-add)を利用します。

この手順は、Intune を設定して、デバイスを管理するために準備に焦点を当てます。

1. **[デバイスがサポートされているを確認](https://docs.microsoft.com/intune/supported-devices-browsers)** します。MacOS、iOS の確認、Intune によって Android、Galaxy では、Windows のデバイスがサポートされています。組織にはではサポートされていないデバイスが含まれている場合、ポリシーは、それらのデバイスに適用されません。

2. **[ドメイン名をカスタマイズ](https://docs.microsoft.com/intune/custom-domain-name-configure)** します。既定では、ドメインの名前が**domain.onmicrosoft.com では、** 自動的には Azure AD のように。**onmicrosoft.com**は、組織に合わせてカスタマイズできます。カスタマイズすると、こともできます一般的なドメインの接続時に Intune とリソースを使用します。

3. **[Intune にサインイン](https://docs.microsoft.com/intune/account-sign-up)** します。サインインするとき、組織に関する情報を入力する必要があります。Intune は、Microsoft 365 に含まれ、 [Office 365 管理ポータル](https://portal.office.com/)から直接開くことができます。Intune は、 [Azure ポータル](https://portal.azure.com)から直接開くこともできます。

4. **[、モバイル デバイス管理の構成を選択](https://docs.microsoft.com/intune/mdm-authority-set)** します。初めて Intune を使用するデバイスの管理を有効にする必要があります。Intune は、クラウド専用サービスで、Intune およびシステム センター構成マネージャーでは、Office 365 でモバイル デバイス管理を使用すると、ハイブリッドとして使用できます。組織に最適な設定を選択します。

5. **[追加ユーザー](https://docs.microsoft.com/intune/users-add)** および**[グループを追加](https://docs.microsoft.com/intune/groups-add)** します。 

   手動でユーザーを追加したり、Intune でユーザーの同期に Azure の AD に接続できます。特定のユーザーに管理者の役割を与えることができます。ユーザーは、デバイスは、キオスク デバイスなどの"userless"のデバイスでない限り必要があります。

   Azure AD グループは、デバイスと Intune でユーザーを管理する方法を簡略化に使用されます。グループを使用すると、さまざまなタスクを実行できます。たとえば、組織では、Android デバイス上の特定のアプリケーションを必要とするが。、Android のデバイス グループを作成し、このアプリケーションのポリシーをグループに配置できます。

    Intune では、ユーザーまたはグループで作成するを追加できます[フェーズ 2: アイデンティティ](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)

6. **[ライセンスを割り当てます](https://docs.microsoft.com/intune/licenses-assign)**。Intune に登録するユーザーまたはデバイス、デバイスのライセンスが必要です。各ユーザーまたはデバイスの userless には、Intune Intune サービスにアクセスするのにはライセンスが必要です。これらのライセンスは、マイクロソフトの 365 に含まれているし、Intune に割り当てる必要があります。

## <a name="step-4-enroll-devices"></a>手順 4: デバイスを登録します。

デバイスを管理するためには、Intune にデバイスを登録する必要があります。管理者は、登録の制限およびユーザーとデバイスのポリシーを設定します。各デバイスのプラットフォーム (iOS、Android、macOS、および Windows) では、さまざまなオプションがあります。ユーザー自身を登録することができます。または、登録を自動化するには、ユーザーがデバイスを単にサインインするようにします。

登録は Intune を使用する場合、重要なステップです。[登録デバイス](https://docs.microsoft.com/intune/device-enrollment)は、さまざまなデバイス用の手順を示します。

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: iOS および Android デバイスの登録](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>手順 5: を追加し、アプリケーションを展開します。

モバイル デバイス上のアプリは、多くの場合最も簡単な方法のユーザーが企業リソースへのアクセスを取得します。 

課題アプリケーションを使用する場合は個人用デバイス、デバイスの企業など、さまざまなデバイスがあります。組織のリソースとそのデータを保護する一方で、ユーザーが生産性を向上します。

Intune などのアプリケーションを管理できるアプリケーションを追加、別のユーザーまたはグループに割り当てる、およびその他の重要な詳細事項を確認します。などをインストールするには、アプリケーション、および複数のバージョンを確認するアプリケーションが失敗するかを確認できます。

ユーザーがモバイル デバイスを取得するとき組織の電子メールやドキュメントにアクセスする最初のタスクの 1 つです。Intune を使用すると、することができます[を作成し電子メールの設定を展開する](https://docs.microsoft.com/intune/email-settings-configure)デバイスに事前にインストールされている電子メール アプリケーションを使用します。 

[追加アプリケーション](https://docs.microsoft.com/intune/app-management)の追加、展開、監視、構成、および、組織内のデバイスにアプリケーションを保護するための手順を一覧表示します。

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テスト ラボ ガイド: デバイス ・ コンプライアンス ・ ポリシー](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>手順 6: は、コンプライアンスと条件付きのアクセスを有効にします。

、前の手順では、環境を設定し、Intune を有効にします。これで、コンプライアンスと条件付きのアクセスを使用していくつかのポリシーを作成する準備ができました。

コンプライアンスと条件付きのアクセスは、デバイスを管理するのには重要です。**[コンプライアンス ・ ポリシー](https://docs.microsoft.com/intune/device-compliance-get-started)** は、組織のリソースを保護するために作成されます。コンプライアンス ・ ポリシーを作成するときは、標準またはのデバイスである必要があります「ベースライン」を定義しています。など、許容可能な (またはできない) の脅威のレベルを選択して jailbroken デバイスをブロックする、パスワードの長さなどを必要とすることがことができます。準拠ではないので、ルールの目的はこれらのデバイスがない場合は、リソースへのアクセスをブロックできます。

これは、「ブロック」**[条件付きのアクセス](https://docs.microsoft.com/intune/conditional-access)** を紹介します。デバイスは、非準拠と見なされます、電子メール、SharePoint、および詳細へのアクセスをブロックできます。

[Azure ポータル](https://portal.azure.com)で Intune では、これらのポリシーを作成し、ユーザーおよびデバイスに適用することができます。ベスト プラクティスとして、小規模、および段階的なアプローチを使用します。たとえば、jailbroken デバイスをブロックする iOS のポリシーを作成します。パイロットまたはテストのグループに (と呼ばれる「割り当てる」Intune の) ポリシーを適用します。初期テストでは後に、、パイロット グループをより多くのユーザーを追加します。段階的なアプローチを使用するには、さまざまな種類のユーザーからのフィードバックを取得できます。

[コンプライアンス ポリシーのデバイスを使い始める](https://docs.microsoft.com/intune/device-compliance-get-started)と[条件付きアクセスとは何ですか。](https://docs.microsoft.com/intune/conditional-access)を開始することができます。

## <a name="step-7-apply-features-and-settings"></a>機能と設定を適用する手順 7。

これらの機能と設定は、Intune の「cool」の一部と見なされると非常に強力な。条件付きのアクセスを使用していくつかのコンプライアンス ・ ポリシーを適用して正常にしたら**デバイスのプロファイル**を作成します。

Intune [Azure ポータル](https://portal.azure.com)を使用して、macOS、iOS、Android、および Windows のデバイス プラットフォームに基づく別のプロファイルを作成できます。たとえば、次のようなことができます。

- 暗号化を含む、BitLocker のさまざまなオプションを有効にするのに 10 の Windows デバイス上のエンドポイントの保護を使用します。
- IOS デバイスにインストールできる承認済みアプリケーションのリストを作成するのにアプリケーションの制限機能を使用します。または、禁止されているアプリケーションの一覧を作成します。
- キオスクの設定を使用すると、キオスク モードで実行している Android のデバイスでどのアプリケーションを使用することができます」を選択します。
- Wi-fi 接続と、macOS を実行しているデバイスで、セキュリティの種類などの設定を適用します。
- その他

[Microsoft Intune デバイス プロファイルは何ですか?](https://docs.microsoft.com/intune/device-profiles)プロファイルについて、プロファイルを作成する方法について説明するに最適の場所です。

注意してください、小規模、段階的なアプローチを使用します。パイロットまたはテストのグループにプロファイルを割り当てます。次に、パイロット グループをさらにプロファイルを割り当てます。

## <a name="step-8-get-to-know-the-other-features"></a>手順 8: を取得、その他の機能を理解するには

Intune では、強力なサービスと多くの機能が含まれています。Intune を使用して行うことができます他のいくつかのタスクを以下に示します。

- Windows[デバイス](https://docs.microsoft.com/intune/windows-update-for-business-configure)でソフトウェアおよびアップデートを管理する & [の Pc](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)、および[iOS](https://docs.microsoft.com/intune/software-updates-ios)デバイス
- [Windows Defender 高度な脅威保護 (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) 、10 の Windows デバイスで有効にして、SharePoint または Exchange Online などの企業リソースへのアクセスを保護するために準拠し、条件付きのアクセスを使用してください
- [見張り](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector)、[シマンテック社](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)では、他の防御のモバイル脅威のパートナーを使用します。
- 発行し、証明書を書き換えるには、[パートナーの証明書機関 (CA)](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview)を追加します。
- 企業ポータル アプリケーション、取得するアプリケーションなどの[、エンド ・ ユーザーに提供するガイダンス](https://docs.microsoft.com/intune/end-user-educate)
- モニター[アプリケーション](https://docs.microsoft.com/intune/apps-monitor)、[デバイスのコンプライアンス](https://docs.microsoft.com/intune/compliance-policy-monitor)を監視、モニター[構成のプロファイル](https://docs.microsoft.com/intune/compliance-policy-monitor)、および監査ログを使用して複数の遠隔測定します。[Intune データ ウェアハウス](https://docs.microsoft.com/intune/reports-nav-create-intune-reports)に接続し、レポートのニーズをさらに多くの BI の電源を使用できます。


## <a name="identity-and-device-access-recommendations"></a>ID とデバイスのアクセスに関する推奨事項

マイクロソフトでは、一連の安全性と生産性の高い従業員を確保するのには[id とデバイスのアクセス](microsoft-365-policies-configurations.md)に関する推奨事項を提供します。デバイスへのアクセスの推奨事項と設定をこの段階では以下の手順の文書で使用します。

- [前提条件](identity-access-prerequisites.md)
- [共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft での Microsoft 365 Enterprise の活用方法

マイクロソフトの IT 専門家の計画し、これらのリソースでは、EMS とデバイスの管理の展開について説明します。

- [Enterprise Mobility + Security による最新のモバイル生産性の管理](https://www.microsoft.com/itshowcase/Article/Content/972/Managing-modern-mobile-productivity-with-Enterprise-Mobility--Security)
- [Microsoft Intune を使用して Windows 10 デバイスでの作業につながる](https://www.microsoft.com/itshowcase/Article/Content/783/Connecting-to-work-on-your-Windows-10-device-with-Microsoft-Intune)
- [Microsoft での iOS、OS X、Android デバイスによる業務効率化を可能にする](https://www.microsoft.com/itshowcase/Article/Content/773/Enabling-mobile-productivity-for-iOS-OS-X-and-Android-devices-at-Microsoft)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 社での Microsoft 365 Enterprise の活用方法

Microsoft 365 で[、モバイル デバイスの管理インフラストラクチャの展開](contoso-mdm.md)を Contoso 社架空ですが、代表的な多国籍企業、クラウドのサービスを参照してください。

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>次の手順

[モバイル デバイス管理インフラストラクチャの終了条件](mobility-infrastructure-exit-criteria.md)

