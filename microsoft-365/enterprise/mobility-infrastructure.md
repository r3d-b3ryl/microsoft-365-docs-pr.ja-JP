---
title: フェーズ 5-モバイルデバイス管理
description: Microsoft 365 Enterprise には、Microsoft Intune を使用したモバイルデバイス管理が含まれます。 要件と前提条件を確認し、Azure Active Directory リソースを使用して Intune を設定し、iOS、macOS、Android、および Windows デバイスを登録し、アプリを展開し、構成プロファイルを作成し、コンプライアンスポリシーを使用して、モバイルの条件付きアクセスを有効にします。Microsoft 365 Enterprise を使用したデバイス管理。
keywords: Microsoft 365、Microsoft 365 Enterprise、Microsoft 365 ドキュメント、モバイルデバイス管理、Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/18/2018
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 0ee9696d441d61fb41359f6502e6f73988749156
ms.sourcegitcommit: 12fbb429dba7517220191d90816e235583943fe0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2019
ms.locfileid: "33623151"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>フェーズ 5: Microsoft 365 Enterprise のモバイルデバイス管理

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*この機能は、Microsoft 365 Enterprise の E3 および E5 バージョンに適用されます。*

Microsoft 365 Enterprise では、組織内のデバイスとアプリを管理するのに役立つ機能が含まれています。 Microsoft Intune を使用すると、iOS、Android、macOS、および Windows デバイスを管理して、組織のリソース (データなど) へのアクセスを保護することができます。 Intune は Azure Active Directory (Azure AD) と統合され、次のビジネスシナリオを Microsoft 365 に対して有効にします。

- 組織内外でファイルを保管および共有して、組織の境界を越えてシームレスに作業を行います
- 柔軟なワーク スタイルを維持しながら、いつでもどこでもデバイスを使って多くのことを安全に成し遂げることができます
- 業界内で確証された世界標準のコンプライアンスに適合したコントロールと可視性により、安心感を提供します
- 情報を保護して、データ損失のリスクを軽減します
- 外部の脅威を検出して保護する
- 組織のセキュリティを迅速に提供するために、アクティビティを監視、報告、および分析する
- ユーザーとそのアカウントを保護する

詳細については、「[Microsoft 365 を使用したデジタル改革](http://transform.microsoft.com)」を参照してください。 

このフェーズでは、デバイスを Intune に登録し、ポリシーを作成して適用し、データのセキュリティ保護と保護を強化します。 Intune ドキュメントのライブラリ全体が[オンラインで提供](https://docs.microsoft.com/intune)されています。 また、開始する前に、 [「Intune 展開の計画、設計、実装ガイド」](https://docs.microsoft.com/intune/planning-guide)を確認することをお勧めします。

## <a name="step-1-plan-for-your-scenario"></a>手順 1: シナリオを計画する

モバイルデバイスを管理する主な理由の1つとして、組織のリソースを保護して保護することが挙げられます。 [Microsoft Intune の一般的な使用方法](https://docs.microsoft.com/intune/common-scenarios)Office 365 の電子メールとデータをセキュリティで保護するなど、いくつかの現実の例を示します。

Intune[は、モバイルデバイス管理 (MDM) またはモバイルアプリケーション管理 (MAM)](https://docs.microsoft.com/intune/byod-technology-decisions)を使用して、組織へのアクセスを管理するためのオプションを提供します。 MDM は、ユーザーが Intune にデバイスを登録するときに行います。 登録されると、管理対象デバイスであり、組織で使用されているすべてのポリシー、ルール、および設定を受け取ることができます。 たとえば、具体的なアプリをインストールしたり、パスワードポリシーを作成したり、VPN 接続をインストールしたりできます。

独自の個人用デバイスを使用しているユーザーは、デバイスを登録したり、Intune およびポリシーで管理したりすることはできません。 ただし、組織のリソースとデータを保護する必要がある場合もあります。 このシナリオでは、MAM を使用してアプリを保護することができます。 たとえば、ユーザーがデバイス上の SharePoint にアクセスするときに PIN を入力する必要がある MAM ポリシーを使用できます。

また、個人または組織所有のデバイスを管理する方法も決定します。 使用方法に応じて、デバイスを異なる方法で扱うことができます。 たとえば、人事 (HR) のユーザーや Sales のユーザーには、さまざまなプランが必要になることがあります。 [モバイルデバイス管理の使用状況を特定する-ケースシナリオ](https://docs.microsoft.com/intune/planning-guide-scenarios)では、開始することができ、これらのさまざまなシナリオについていくつかのガイダンスが含まれています。

## <a name="step-2-get-your-prerequisites"></a>手順 2: 前提条件を取得する

次に、要件と前の手順で作成したシナリオに基づいて、前提条件を取得します。 [計画を実装](https://docs.microsoft.com/intune/planning-guide-onboarding)するすべての要件を一覧表示します。 以下は、Microsoft 365 を使用した Intune に必要な重要なアイテムです。

- **Intune サブスクリプション**: microsoft 365 に同梱されており、 [Azure Portal](https://portal.azure.com)で microsoft Intune にアクセスすることができます。
- **Office 365 サブスクリプション**: Microsoft 365 に含まれており、電子メールを含む office アプリに使用されます。
- **Azure Active Directory (AZURE AD) premium**: Microsoft 365 に含まれており、ユーザーまたはセキュリティグループを作成するために使用されます。 これらのグループは、ユーザーが作成した Intune ポリシーを受信します。たとえば、デバイスのロックを解除するためのパスワードの長さを強制します。 [フェーズ 2: Identity](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)で作成したグループを使用できます。

組織のニーズによっては、追加の要件がある場合があります。 たとえば、iOS デバイスを管理する場合は、Apple MDM プッシュ証明書が必要になります。 オンプレミスの Exchange を使用している場合は、オンプレミスの Exchange コネクタが必要になります。 これらの追加要件については、これらの手順を実行するときに説明されています。

## <a name="step-3-set-up-intune"></a>手順 3: Intune をセットアップする

Intune では、ドメイン、ユーザー、グループなど、Azure AD の多くの機能が使用されます。 また、企業のニーズに合わせて新しいユーザーおよび新しいグループを作成することもできます。 たとえば、 **iOS デバイス**または**すべての人事ユーザー**と呼ばれるグループを作成できます。  [動的グループ](https://docs.microsoft.com/intune/groups-add)を活用して、単純なまたは詳細なルールに基づいてユーザーまたはデバイスグループを作成できます。

この手順では、Intune のセットアップと、デバイスを管理するための準備について説明します。

1. **[デバイスがサポートされていることを確認](https://docs.microsoft.com/intune/supported-devices-browsers)** します。 IOS、macOS、Android、Galaxy、Windows デバイスが Intune によってサポートされていることを確認します。 サポートされていないデバイスが組織に含まれている場合、それらのデバイスにポリシーは適用されません。

2. **[ドメイン名をカスタマイズ](https://docs.microsoft.com/intune/custom-domain-name-configure)** します。 既定では、 **your-domain.onmicrosoft.com**のような名前のドメインが Azure AD に自動的に作成されます。 **onmicrosoft.com**は、組織に合わせてカスタマイズできます。 カスタマイズすると、ユーザーは Intune に接続するときやリソースを使用するときに、使い慣れたドメインになることができます。

3. **[Intune にサインイン](https://docs.microsoft.com/intune/account-sign-up)** します。 サインインするときに、組織に関する情報の入力を求められることがあります。 Intune は Microsoft 365 に含まれており、 [microsoft 365 管理センター](https://admin.microsoft.com)から直接開くことができます。 [Azure ポータル](https://portal.azure.com)から直接 Intune を開くこともできます。

4. **[モバイルデバイス管理の構成を選択](https://docs.microsoft.com/intune/mdm-authority-set)** します。 初めて Intune を使用するときは、デバイスの管理を有効にする必要があります。 Intune は、クラウドのみのサービスとして、Intune および System Center Configuration Manager を使用したハイブリッドとして、または Office 365 用のモバイルデバイス管理を使用して使用できます。 組織に最も適したセットアップを選択できます。

5. **[ユーザーを追加](https://docs.microsoft.com/intune/users-add)** し、**[グループを追加](https://docs.microsoft.com/intune/groups-add)** します。 

   ユーザーを手動で追加したり、Azure AD に接続してユーザーを Intune と同期させることができます。 特定のユーザーに管理者ロールを付与することもできます。 ユーザーは、デバイスがキオスクデバイスなどの "userless" デバイスでない限り、必要になります。

   Azure AD グループは、Intune でのデバイスとユーザーの管理を簡素化するために使用されます。 グループを使用すると、さまざまなタスクを実行できます。 たとえば、組織が Android デバイスで特定のアプリを必要とするとします。 Android デバイスグループを作成して、このアプリを使用したポリシーをグループに展開することができます。

    Intune では、「[フェーズ 2: id](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) 」で作成したユーザーまたはグループを追加できます。

6. **[ライセンスを割り当て](https://docs.microsoft.com/intune/licenses-assign)** ます。 ユーザーまたはデバイスが Intune に登録するには、デバイスのライセンスが必要です。 ユーザーまたはユーザーが少ないデバイスでは、intune サービスにアクセスするために Intune ライセンスが必要です。 これらのライセンスは、Microsoft 365 に含まれており、Intune で割り当てられている必要があります。

## <a name="step-4-enroll-devices"></a>手順 4: デバイスの登録

デバイスを管理するには、デバイスを Intune に登録する必要があります。 管理者は、ユーザーとデバイスの登録の制限とポリシーを設定します。 各デバイスプラットフォーム (iOS、Android、macOS、Windows) には、さまざまなオプションがあります。 ユーザーが自分を登録することができます。 または、ユーザーが簡単にデバイスにサインインできるように登録を自動化することもできます。

登録は、Intune を使用する際の重要な手順です。 [デバイスの登録](https://docs.microsoft.com/intune/device-enrollment)さまざまなデバイスの手順を示します。

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テストラボガイド: iOS および Android デバイスの登録](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>手順 5: アプリを追加して展開する

多くの場合、モバイルデバイス上のアプリは、ユーザーが企業リソースにアクセスする最も簡単な方法です。 

アプリを使用する際には、個人デバイスや企業デバイスなどのさまざまなデバイスがあるため、課題があります。 また、組織のリソースとそのデータを保護し、ユーザーの生産性を高めることも必要になります。

Intune では、アプリの追加、他のユーザーまたはグループへのアプリの割り当て、その他の重要な詳細の確認などのアプリの管理を行うことができます。 たとえば、インストールに失敗したアプリを確認したり、アプリのバージョンなどを確認したりできます。

ユーザーがモバイルデバイスを取得する場合、最初のタスクの1つとして、組織の電子メールとドキュメントへのアクセスがあります。 Intune を使用すると、デバイスに事前にインストールされている電子メールアプリを使用して[電子メール設定を作成して展開](https://docs.microsoft.com/intune/email-settings-configure)できます。 

[[アプリの追加](https://docs.microsoft.com/intune/app-management)] には、組織内のデバイス上のアプリを追加、展開、監視、構成、保護する手順が一覧表示されます。

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [テストラボガイド: デバイスコンプライアンスポリシー](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>手順 6: コンプライアンスおよび条件付きアクセスを有効にする

前の手順では、環境を設定し、Intune を有効にします。 これで、コンプライアンスと条件付きアクセスを使用して、いくつかのポリシーを作成する準備が整いました。

デバイスを管理するには、コンプライアンスおよび条件付きアクセスが重要です。 組織のリソースを保護するために、**[コンプライアンスポリシー](https://docs.microsoft.com/intune/device-compliance-get-started)** が作成されます。 コンプライアンスポリシーを作成する場合、デバイスに必要な標準または "ベースライン" を定義しています。 たとえば、許容できる (または許容されない) 脅威レベルを選択したり、脱獄デバイスをブロックしたり、パスワードの長さを要求したりできます。 これらのデバイスが規制に準拠していない場合は、リソースへのアクセスをブロックすることができます。

この "ブロック" は、**[条件付きアクセス](https://docs.microsoft.com/intune/conditional-access)** を導入します。 デバイスが準拠していないと見なされた場合は、電子メール、SharePoint などへのアクセスをブロックすることができます。

[Azure portal](https://portal.azure.com)の Intune を使用すると、これらのポリシーを作成し、ユーザーとデバイスに適用できます。 ベストプラクティスとして、少し開始し、段階的なアプローチを使用します。 たとえば、脱獄デバイスをブロックする iOS ポリシーを作成します。 パイロットまたはテストグループへのポリシーの適用 (Intune での「割り当て」と呼ばれます)。 初期テストの後、パイロットグループにユーザーを追加します。 段階的な手法を使用すると、さまざまなユーザーの種類からフィードバックを得ることができます。

[デバイスコンプライアンスポリシー](https://docs.microsoft.com/intune/device-compliance-get-started)と[条件付きアクセスの](https://docs.microsoft.com/intune/conditional-access)概要については、開始する際に役立ちます。

## <a name="step-7-apply-features-and-settings"></a>手順 7: 機能と設定を適用する

これらの機能と設定は、多くの場合、Intune の "クールな" 部分と見なされ、非常に強力です。 条件付きアクセスを使用してコンプライアンスポリシーを正常に適用すると、**デバイスプロファイル**を作成する準備が整います。

[Azure portal](https://portal.azure.com)の Intune を使用すると、デバイスプラットフォーム (IOS、MacOS、Android、Windows) に基づいて、さまざまなプロファイルを作成できます。 たとえば、次のように操作できます。

- Windows 10 デバイスで Endpoint protection を使用して、暗号化などのさまざまな BitLocker オプションを有効にします。
- IOS デバイスで制限付きアプリ機能を使用して、インストール可能な承認済みアプリの一覧を作成します。 または、禁止されているアプリのリストを作成します。
- キオスクの設定を使用して、キオスクモードで実行されている Android デバイスで使用できるアプリを選択します。
- MacOS を実行しているデバイスに、Wi-fi 接続とその設定 (セキュリティの種類を含む) を適用します。
- その他

[Microsoft Intune デバイスプロファイルとは](https://docs.microsoft.com/intune/device-profiles)プロファイルについての情報を読んで、プロファイルを作成する方法などを確認するのに最適な場所です。

少し開始して、段階的なアプローチを使用してください。 パイロットまたはテストグループにプロファイルを割り当てます。 その後、プロファイルをパイロットグループに割り当てます。

## <a name="step-8-get-to-know-the-other-features"></a>手順 8: その他の機能を理解する

Intune は強力なサービスで、多くの機能を備えています。 Intune を使用して実行できるその他のタスクを次に示します。

- Windows[デバイス](https://docs.microsoft.com/intune/windows-update-for-business-configure) & [pc](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)、 [iOS](https://docs.microsoft.com/intune/software-updates-ios)デバイスのソフトウェアと更新プログラムを管理する
- Windows 10 デバイスで[Windows Defender Advanced Threat Protection (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection)を有効にし、コンプライアンスおよび条件付きアクセスを使用して、SharePoint や Exchange Online などの企業リソースへのアクセスを保護します。
- [見張り](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector)、 [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)、その他のモバイル防御の脅威パートナーを使用する
- [パートナー証明機関 (CA)](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview)を追加して証明書を発行および更新する
- 企業ポータルアプリの[エンドユーザーにガイダンスを提供](https://docs.microsoft.com/intune/end-user-educate)し、アプリを取得する
- 監査ログを使用して、[アプリ](https://docs.microsoft.com/intune/apps-monitor)の監視、[デバイスのコンプライアンス](https://docs.microsoft.com/intune/compliance-policy-monitor)の監視、[構成プロファイル](https://docs.microsoft.com/intune/compliance-policy-monitor)の監視、およびその他のテレメトリを行います。 また、 [Intune データウェアハウス](https://docs.microsoft.com/intune/reports-nav-create-intune-reports)に接続して、さらにレポートを必要とする power BI を使用することもできます。


## <a name="identity-and-device-access-recommendations"></a>ID とデバイスのアクセスに関する推奨事項

Microsoft では、セキュアで生産性の高い労働力を確保するために [ID とデバイスのアクセス](microsoft-365-policies-configurations.md)に関する一連の推奨事項を提供しています。 デバイスアクセスの場合は、このフェーズの手順と共に次の記事の推奨事項と設定を使用します。

- [前提条件](identity-access-prerequisites.md)
- [共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft での Microsoft 365 Enterprise の活用方法

Microsoft の IT 専門家[が EMS を使用してデバイスを管理](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR8)する方法について説明します。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 社での Microsoft 365 Enterprise の活用方法

架空の多国籍企業である Contoso Corporation が、Microsoft 365 cloud services を使用して[モバイルデバイス管理インフラストラクチャを展開](contoso-mdm.md)した方法について説明します。

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>次の手順

[モバイルデバイス管理インフラストラクチャの終了条件](mobility-infrastructure-exit-criteria.md)

