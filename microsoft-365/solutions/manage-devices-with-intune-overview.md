---
title: Intune でデバイスを管理する
ms.author: bcarter
author: brendacarter
f1.keywords:
- enroll devices into Intune
- manage device endpoints
- zero trust deployment stack
- device management with zero trust
manager: dougeby
audience: ITPro
ms.topic: article
description: エンドポイント デバイスをゼロ トラスト セキュリティ アーキテクチャの一部として Microsoft Intune に登録し、リモート ワーカーの保護を構築しながら、ランサムウェアから保護します。
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-managedevices
- m365solution-overview
ms.custom: ''
keywords: ''
ms.openlocfilehash: 08abc5c53c54c5a4e4100cc88adf0fb25af5c23b
ms.sourcegitcommit: e624221597480295b799d56568c4f6f56d40b41d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2022
ms.locfileid: "65535362"
---
# <a name="manage-devices-with-intune-overview"></a>Intune の概要でデバイスを管理する

エンタープライズ レベルのセキュリティのコア コンポーネントには、デバイスの管理と保護が含まれます。 ゼロトラスト セキュリティ アーキテクチャを構築する場合でも、ランサム ウェアに対する環境を強化する場合でも、リモート ワーカーをサポートするための保護を組み込む場合でも、デバイスの管理は戦略の一部です。
Microsoft 365 には、デバイスを管理および保護するためのツールと方法論がいくつか含まれていますが、このガイダンスでは、Microsoft Intune を使用した Microsoft の推奨事項について説明します。 これは、次の場合に適切なガイダンスです。

- Azure AD 結合 (Hybrid Azure AD 結合を含む) を介してデバイスを Intune に登録することを計画します。
- デバイスを手動で Intune に登録することを計画します。
- アプリとデータの保護を実装する計画のある BYOD デバイスを許可するか、これらのデバイスを Intune に登録します。

一方、環境に Microsoft Endpoint Configuration Manager を含む共同管理の計画が含まれている場合は、[共同管理ドキュメント](/mem/configmgr/comanage/)を参照して、組織に最適なパスを開発してください。 ご使用の環境に Windows 365 Cloud PC の計画が含まれている場合は、[Windows 365 エンタープライズのドキュメント](/windows-365/enterprise/)を参照して、組織に最適なパスを開発してください。

このビデオでは、展開プロセスの概要について説明します。
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Y4fC]


## <a name="why-manage-endpoints"></a>エンドポイントを管理する理由

現代の企業には、データにアクセスするエンドポイントの驚くほどの多様性があります。 このセットアップにより、大規模な攻撃対象領域が作成され、その結果、エンドポイントがゼロ トラスト セキュリティ戦略の最も弱いリンクになる可能性があります。

世界がリモートまたはハイブリッドの作業モデルに移行するにつれ、主に必要性に駆り立てられて、ユーザーは、これまでのどの時代よりも、どこからでも、どのデバイスからでも作業を行っています。 攻撃者は、この変更を利用するために戦術をすばやく調整しています。 多くの組織は、これらの新しいビジネス上の課題に対処する際に、リソースの限界に直面しています。 事実上一夜にして、企業はデジタル変革を加速させています。 簡単に言うと、人々の働き方が変わりました。オフィスや会社所有のデバイスからのみ、無数の企業リソースにアクセスすることはもはや期待できません。

企業リソースにアクセスするエンドポイントを可視化することは、ゼロ トラスト デバイス戦略の最初のステップです。 通常、企業は PC を脆弱性や攻撃から保護することに積極的ですが、モバイル デバイスは監視も保護もされていないことがよくあります。 データをリスクにさらさないようにするには、すべてのエンド ポイントでリスクを監視し、きめ細かいアクセス制御を採用して、組織のポリシーに基づいて適切なレベルのアクセスを提供する必要があります。 たとえば、個人用デバイスが脱獄された場合、アクセスをブロックして、エンタープライズ アプリケーションが既知の脆弱性にさらされないようにすることができます。

この一連の記事では、リソースにアクセスするデバイスを管理するための推奨プロセスについて説明します。 推奨される手順に従うと、組織はデバイスやデバイスがアクセスするリソースに対して非常に高度な保護を実現できます。

## <a name="implementing-the-layers-of-protection-on-and-for-devices"></a>デバイス上およびデバイスの保護レイヤーの実装

デバイス上のデータとアプリ、およびデバイス自体を保護することは、多層プロセスです。 管理されていないデバイスで取得できる保護がいくつかあります。 デバイスを管理に登録した後、より高度なコントロールを実装できます。 脅威保護がエンドポイント全体に展開されると、さらに多くの分析情報が得られ、一部の攻撃を自動的に修正する機能が得られます。 最後に、組織が機密データの識別、分類とラベルの適用、および Microsoft Purview データ損失防止ポリシーの構成に取り組んでいる場合は、エンドポイント上のデータをさらにきめ細かく保護できます。

次の図は、この環境に導入する Microsoft 365 およびその他の SaaS アプリのゼロ トラスト セキュリティ ポスチャを実現するためのビルディング ブロックを示しています。 デバイスに関連する要素には、1 から 7 までの番号が付けられています。 これらは、デバイス管理者が他の管理者と調整して達成する保護の層です。

![Microsoft 365 ゼロトラスト展開スタック](../media/devices/m365-zero-trust-deployment-stack-devices.png#lightbox)

この図について:

|&nbsp;|手順|説明|ライセンスの要件|
|---|---|---|---|
|1|開始点のゼロトラスト ID およびデバイス アクセス ポリシーを構成します|ID 管理者と協力して、[**レベル 2 のアプリ保護ポリシー (APP) データ保護を実装します**](manage-devices-with-intune-app-protection.md)。 これらのポリシーでは、デバイスを管理する必要はありません。 Intune で APP ポリシーを構成します。 ID 管理者は、承認されたアプリを要求するように条件付きアクセス ポリシーを構成します。|E3、E5、F1、F3、F5|
|2|デバイスを Intune に登録する|このタスクを実装するには、より多くの計画と時間が必要です。 このツールは最適な統合を提供するため、Microsoft は Intune を使用してデバイスを登録することをお勧めします。 プラットフォームに応じて、デバイスを登録するためのいくつかのオプションがあります。 たとえば、Windows デバイスは、Azure AD Join または Autopilot を使用して登録できます。 各プラットフォームのオプションを確認し、ご使用の環境に最適な登録オプションを決定する必要があります。 詳細については、「[**手順 2 — デバイスを Intune に登録する**](manage-devices-with-intune-enroll.md)」を参照してください。|E3、E5、F1、F3、F5|
|3|コンプライアンス ポリシーの構成|アプリやデータにアクセスしているデバイスが最小要件を満たしていることを確認する必要があります。たとえば、デバイスがパスワードまたは PIN で保護されており、オペレーティング システムが最新であることです。 コンプライアンス ポリシーは、デバイスが満たす必要のある要件を定義する方法です。 「[**手順 3. コンプライアンス ポリシーの設定**](manage-devices-with-intune-compliance-policies.md)」は、これらのポリシーを構成するのに役立ちます。|E3、E5、F3、F5|
|4|エンタープライズ (推奨) ゼロ トラスト ID およびデバイス アクセス ポリシーの構成|デバイスが登録されたので、ID 管理者と協力して、[**条件付きアクセス ポリシーを微調整し、正常で準拠したデバイスを要求**](manage-devices-with-intune-require-compliance.md)できます。|E3、E5、F3、F5|
|5|構成プロファイルの展開|設定した基準に基づいてデバイスを準拠または非準拠としてマークするだけのデバイス コンプライアンス ポリシーとは対照的に、構成プロファイルは実際にデバイスの設定の構成を変更します。 構成ポリシーを使用して、サイバー脅威に対してデバイスを強化できます。 「[**手順 5. 構成プロファイルを展開する**](manage-devices-with-intune-configuration-profiles.md)」を参照してください。|E3、E5、F3、F5|
|6 |デバイスのリスクとセキュリティ ベースラインへのコンプライアンスを監視する|この手順では、Intune を Microsoft Defender for Endpoint に接続します。 この統合により、アクセスの条件としてデバイスのリスクを監視できます。 危険な状態にあることが判明したデバイスはブロックされます。 セキュリティ基準計画への準拠を監視することもできます。 「[**手順 6. デバイスのリスクとセキュリティ基準計画への準拠を監視する**](manage-devices-with-intune-monitor-risk.md)」を参照してください。|E5、F5|
|7 |情報保護機能を備えたデータ損失防止 (DLP) を実装する|組織が機密データの識別とドキュメントのラベル付けに取り組んでいる場合は、情報保護管理者と協力して、[**デバイス上の機密情報とドキュメントを保護できます**](manage-devices-with-intune-dlp-mip.md)。|E5、F5 コンプライアンス アドオン|

## <a name="coordinating-endpoint-management-with-zero-trust-identity-and-device-access-policies"></a>エンドポイント管理とゼロ トラスト IDおよびデバイス アクセス ポリシーの調整

このガイダンスは、推奨される [**ゼロ トラスト ID およびデバイス アクセス ポリシー**](../security/office-365-security/microsoft-365-policies-configurations.md)と緊密に連携しています。 ID チームと協力して、Intune で構成した保護を Azure AD の条件付きアクセス ポリシーに適用します。

これは、Intune/MEM で実行する作業のステップ コールアウトを含む推奨ポリシーセットと、Azure AD での調整に役立つ関連する条件付きアクセス ポリシーの図です。

[![ゼロトラスト ID とデバイス アクセス ポリシー](../media/devices/identity-device-overview-steps.png#lightbox)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/devices/identity-device-overview-steps.png)

この図について:

- 手順 1、[**レベル 2 アプリ保護ポリシー (APP)**](manage-devices-with-intune-app-protection.md) の実装では、APP ポリシーを使用して推奨レベルのデータ保護を構成します。 次に、ID チームと協力して、この保護の使用を要求するように関連する条件付きアクセスルールを構成します。
- 手順 2、3、4 では、デバイスを Intune を使用して管理に登録し、デバイス コンプライアンス ポリシーを定義してから、ID チームと調整して、準拠デバイスへのアクセスのみを許可するように関連する条件付きアクセス ルールを構成します。

<!---
## Managing change with users
--->

## <a name="enrolling-devices-vs-onboarding-devices"></a>デバイスの登録とオンボーディング デバイス

このガイダンスに従うと、Intune を使用してデバイスを管理に登録し、次の Microsoft 365 機能でデバイスをオンボードします。

- Microsoft Defender for Endpoint
- Microsoft Purview (エンドポイントのデータ損失防止 (DLP)) 

次の図は、Intune を使用してこれがどのように機能するかを示しています。

![デバイスの登録とオンボーディングのプロセス](../media/devices/devices-enroll-onboard-process.png#lightbox)

この図について:

1. Intune を使用してデバイスを管理に登録します。
2. Intune を使用して、デバイスを Defender for Endpoint にオンボードします。
3. Defender for Endpoint にオンボードされているデバイスは、Endpoint DLP を含む Microsoft Purview 機能にもオンボードされています。
 
Intune のみがデバイスを管理していることに注意してください。 オンボーディングとは、デバイスが特定のサービスと情報を共有する機能を指します。 次の表は、特定のサービスの管理デバイスとオンボーディング デバイスへのデバイスの登録の違いをまとめたものです。


|         |登録     |オンボード  |
|---------|---------|---------|
|説明     |  登録はデバイスの管理に適用されます。 デバイスは、Intune または Configuration Manager で管理するために登録されます。        | オンボーディングは、Microsoft 365 の特定の機能セットで動作するようにデバイスを構成します。 現在、オンボーディングは、Microsoft Defender for Endpoint および Microsoft コンプライアンス機能に適用されます。 <br><br>Windows デバイスでは、オンボーディングには、Windows Defender の設定を切り替えて、Defender がオンライン サービスに接続し、デバイスに適用されるポリシーを受け入れることができるようにすることが含まれます。        |
|範囲     | これらのデバイス管理ツールは、セキュリティなどの特定の目的を満たすようにデバイスを構成することを含め、デバイス全体を管理します。        |オンボーディングは、適用されるサービスにのみ影響します。     |
|推奨される方法     | Azure Active Directory に参加すると、デバイスが Intune に自動的に登録されます。        | Intune は、Windows Defender for Endpoint にデバイスをオンボーディングするための推奨される方法であり、その結果、Microsoft Purview 機能になります。<br><br>他の方法を使用して Microsoft Purview 機能にオンボードされているデバイスは、Defender for Endpoint に自動的に登録されないことに注意してください。        |
|その他の方法     |   その他の登録方法は、デバイスのプラットフォームと、BYOD であるか、組織によって管理されているかによって異なります。      | デバイスをオンボーディングする他の方法には、推奨される順序が含まれます。<br><li>構成マネージャー<li>その他のモバイル デバイス管理ツール (デバイスが 1 つで管理されている場合)<li>ローカル スクリプト<li>非永続仮想デスクトップ インフラストラクチャ (VDI) デバイスをオンボーディングするための VDI 構成パッケージ<li>グループ ポリシー|
| | |     |


## <a name="learning-for-administrators"></a>管理者向けの学習

次のリソースは、管理者が MEM と Intuneの使用に関する概念を学ぶのに役立ちます。

[Microsoft Endpoint Manager を使用してデバイス管理を簡素化する](/learn/modules/simplify-device-management-with-microsoft-endpoint-manager/) 説明: 最新の管理と Microsoft エンドポイント マネージャー、および Microsoft 365 のビジネス管理ツールですべてのデバイスの管理を簡素化する方法について学習します。

[Microsoft Intune の設定](/learn/modules/set-up-microsoft-intune/) 説明: Microsoft Endpoint Manager の一部である Microsoft Intune は、組織の人々が生産性を高めるために使用するデバイス、アプリ、およびデータを保護するのに役立ちます。 このモジュールを完了すると、Microsoft Intune が設定されます。 設定には、サポートされている構成の確認、Intune へのサイン アップ、ユーザーとグループの追加、ユーザーへのライセンスの割り当て、管理者権限の付与、および MDM 権限の設定が含まれます。
