---
title: 在宅勤務をサポートするセキュリティ チームのトップ 12 タスク
f1.keywords:
- CSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- remotework
description: ランサムウェア、フィッシング、悪意のある添付ファイルなどのサイバー脅威からビジネス メールとデータを保護します。
ms.openlocfilehash: a1850438d02042ba5931a6208b82f74766ae0be8
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097272"
---
# <a name="top-12-tasks-for-security-teams-to-support-working-from-home"></a>在宅勤務をサポートするセキュリティ チームの上位 12 のタスク

Microsoft と同じ [で](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) 、主にホームベースの従業員をサポートしている場合は、組織が可能な限り安全に作業を行うのを支援したいと考えています。 この記事では、セキュリティ チームが最も重要なセキュリティ機能を可能な限り迅速に実装するのに役立つタスクを優先します。

![これらのトップ タスクを実行して、在宅勤務をサポートします。](../media/security/security-support-remote-work.png)

Microsoft のビジネス プランのいずれかを使用している小規模または中規模の組織の場合は、代わりに次のリソースを参照してください。

- [ビジネス 向け 365 Office Microsoft 365 をセキュリティで保護する上位 10 の方法](../admin/security-and-compliance/secure-your-business-data.md)
- [Microsoft 365 for Campaigns](https://docs.microsoft.com/microsoft-365/campaigns/) (Microsoft 365 Business の推奨セキュリティ構成を含む)

Microsoft のエンタープライズ プランを使用しているお客様には、サービス プランに適用される次の表に示すタスクを完了してください。 Microsoft 365 Enterprise プランを購入する代わりに、サブスクリプションを組み合わせる場合は、次の点に注意してください。

- Microsoft 365 E3 には Enterprise Mobility + Security (EMS) E3 と Azure AD P1 が含まれています
- Microsoft 365 E5 には EMS E5 と Azure AD P2 が含まれています

****

|手順|Task|すべての Office 365 Enterprise プラン|Microsoft 365 E3|Microsoft 365 E5|
|---|---|---|---|---|
|1 |[Azure AD多要素認証 (MFA) を有効にする](#1-enable-azure-ad-multi-factor-authentication-mfa)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2|[脅威からの保護](#2-protect-against-threats)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3|[Microsoft Defender を Office 365 用に構成する](#3-configure-microsoft-defender-for-office-365)|||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4 |[Id 用に Microsoft Defender を構成する](#4-configure-microsoft-defender-for-identity)|||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5 |[Microsoft 365 Defender を有効にする](#5-turn-on-microsoft-365-defender)|||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6 |[電話とタブレット用に Intune モバイル アプリ保護を構成する](#6-configure-intune-mobile-app-protection-for-phones-and-tablets)||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7 |[ゲストの MFA と条件付きアクセス (Intune アプリ保護を含む) を構成する](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8 |[PC をデバイス管理に登録し、準拠した PC を必要とする](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9 |[クラウド接続用にネットワークを最適化する](#9-optimize-your-network-for-cloud-connectivity)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10 |[ユーザーのトレーニング](#10-train-users)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|11|[Microsoft Cloud App Security の使用を開始する](#11-get-started-with-microsoft-cloud-app-security)|||![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|12 |[脅威を監視し、アクションを実行する](#12-monitor-for-threats-and-take-action)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

開始する前に [、Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) セキュリティ センターで Microsoft 365 セキュア スコアを確認してください。 一元的なダッシュボードから、Microsoft 365 ID、データ、アプリ、デバイス、インフラストラクチャのセキュリティを監視し、強化できます。 推奨されるセキュリティ機能の構成、セキュリティ関連のタスクの実行 (レポートの表示など)、またはサード パーティ製のアプリケーションまたはソフトウェアを使用した推奨事項への対処を行うポイントが与えられる。 この記事で推奨されるタスクは、スコアを上げる可能性があります。

![Microsoft セキュア スコアのスクリーンショット](../media/secure-score.png)

## <a name="1-enable-azure-ad-multi-factor-authentication-mfa"></a>1: Azure AD多要素認証 (MFA) を有効にする

在宅勤務の従業員のセキュリティを向上させるためにできる唯一の最善の方法は、MFA を有効にすることです。 プロセスをまだ実施していない場合は、このプロセスを緊急パイロットとして扱い、行き詰まった従業員を支援するサポートフォークを用意してください。 ハードウェア セキュリティ デバイスを配布できない可能性が高い場合は、Windows Hello 生体認証と Microsoft Authenticator などのスマートフォン認証アプリを使います。

通常は、MFA を要求する前に、ユーザーに多要素認証の登録を 14 日間お勧めします。 しかし、従業員が突然自宅で働いている場合は、セキュリティの優先順位として MFA を要求し、必要なユーザーを支援する準備をします。

これらのポリシーの適用には数分しかかからなく、数日後にユーザーをサポートする準備が必要になります。

****

|計画|推奨事項|
|---|---|
|Microsoft 365 プラン (Azure AD P1 または P2 なし)|[Azure AD でセキュリティの既定値を有効にします](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。 Azure AD のセキュリティの既定値には、ユーザーと管理者用の MFA が含まれています。|
|Microsoft 365 E3 (Azure AD P1 を使用)|[一般的な条件付きアクセス ポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)を使用して、次のポリシーを構成します。 <br/>- [管理者に MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br/>- [すべてのユーザーに MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br/> - [従来の認証をブロックする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)|
|Microsoft 365 E5 (Azure AD P2 を使用)|Azure AD Identity Protection を利用して、次の 2 つのポリシーを作成して、Microsoft の[条件付きアクセスと関連ポリシーの推奨されるセット](./office-365-security/identity-access-policies.md)の実装を開始します。<br/> - [サインインのリスクが中、または高のときに MFA を要求する](./office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br/>- [先進認証をサポートしないクライアントはブロックする](./office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)<br/>- [高リスク ユーザーはパスワードを変更する必要がある](./office-365-security/identity-access-policies.md#high-risk-users-must-change-password)|
|

## <a name="2-protect-against-threats"></a>2: 脅威から保護する

すべての Microsoft 365 プランには、さまざまな脅威保護機能が含まれます。 これらの機能の保護を強化するには、数分かかります。

- マルウェア対策保護
- 悪意のある URL とファイルからの保護
- フィッシング対策保護
- スパム対策保護

開始 [点として使用できるガイダンスについては、「Office 365](office-365-security/protect-against-threats.md) の脅威から保護する」を参照してください。

## <a name="3-configure-microsoft-defender-for-office-365"></a>3: Microsoft Defender を Office 365 用に構成する

Microsoft 365 E5 および Office 365 E5 に付属する Office 365 用 Microsoft Defender は、電子メール メッセージ、リンク (URL)、コラボレーション ツールによって生じ得る悪意のある脅威から組織を保護します。 構成には数時間かかる場合があります。

Microsoft Defender for Office 365:

- 添付ファイルや悪意のあるコンテンツのリンクを検査するインテリジェント システムを使用して、未知の電子メールの脅威からリアルタイムで組織を保護します。 これらの自動化システムには、堅牢なデトレーション プラットフォーム、ヒューリスティック、機械学習モデルが含まれます。
- ユーザーが共同作業を行い、ファイルを共有するときに、チーム サイトとドキュメント ライブラリで悪意のあるファイルを識別してブロックすることで、組織を保護します。
- 機械学習モデルと高度な偽装検出アルゴリズムを適用して、フィッシング攻撃を回避します。

プランの概要など、概要については [、「Defender for Office 365」](office-365-security/office-365-atp.md)を参照してください。

グローバル管理者は、次の保護を構成できます。

- [安全なリンク ポリシーを設定する](office-365-security/set-up-atp-safe-links-policies.md)
- [安全なリンクのグローバル設定を構成する](office-365-security/configure-global-settings-for-safe-links.md)
- [安全な添付ファイル ポリシーを設定する](office-365-security/set-up-atp-safe-attachments-policies.md)

Exchange Online 管理者と SharePoint Online 管理者と一緒に作業し、次のワークロード用に Office 365 用に Defender を構成する必要があります。

- [SharePoint、OneDrive、Microsoft Teams 用の ATP](office-365-security/atp-for-spo-odb-and-teams.md)

## <a name="4-configure-microsoft-defender-for-identity"></a>4: Id 用に Microsoft Defender を構成する

[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) はクラウドベースのセキュリティ ソリューションであり、オンプレミスの Active Directory のシグナルを活用して、組織に対する高度な脅威、ID の漏えい、内部関係者の不正な行動を特定、検出、調査します。 次は、プレマムとクラウド インフラストラクチャを保護し、依存関係や前提条件を持たないので、すぐにメリットを得るために、この方法に重点を置いて説明します。

- セットアップ [を迅速に行う場合は、「Id](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) クイックスタート用 Microsoft Defender」をご覧ください。
- ビデオ [を見る: Id 用 Microsoft Defender の概要](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- Id の [展開のための Microsoft Defender の 3 つのフェーズを確認する](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="5-turn-on-microsoft-365-defender"></a>5: Microsoft 365 Defender を有効にする

Office 365 用の Microsoft Defender と Id 用 Microsoft Defender が構成されたので、これらの機能からのシグナルを 1 つのダッシュボードで表示できます。 [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) は、アラート、インシデント、自動調査と対応、ワークロード間の高度な捜ティング (Microsoft Defender for Identity、Office 365 用 Defender、エンドポイント用 Microsoft Defender、Microsoft Cloud App Security) を [security.microsoft.com](https://security.microsoft.com)の単一ウィンドウにまとめます。

![MTP ダッシュボードの図](../media/top-ten-security-remote-work-mtp-dashboard.png)

365 サービス用に 1 つ以上の Defender をOffice、MTP を有効にしてください。 MTP には新機能が継続的に追加されます。プレビュー機能を受け取るオプトインを検討してください。

- [MTP について詳しくは、次のリンクを参照してください。](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [MTP を有効にする](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)
- [プレビュー機能をオプトインする](https://docs.microsoft.com/microsoft-365/security/mtp/preview)

## <a name="6-configure-intune-mobile-app-protection-for-phones-and-tablets"></a>6: 電話とタブレット用に Intune モバイル アプリ保護を構成する

Microsoft Intune Mobile Application Management (MAM) を使用すると、これらのデバイスを管理することなく、電話やタブレット上の組織のデータを管理および保護できます。 次に、動作のしくみを示します。

- アプリ保護ポリシー (APP) を作成して、デバイス上でどのアプリを管理し、どのような動作を許可できるのかを決定します (管理対象アプリのデータがアンマネージ アプリにコピーされるのを防ぐなど)。 プラットフォームごとに 1 つのポリシー (iOS、Android) を作成します。
- アプリ保護ポリシーを作成した後、Azure AD で条件付きアクセス ルールを作成して、承認されたアプリとアプリ データ保護を要求することで、これらを適用します。

アプリ保護ポリシーには多くの設定が含まれます。 幸いなことに、すべての設定について学び、オプションの重み付けする必要があるというのではありません。 Microsoft では、開始点を推奨することで、設定の構成を簡単に適用できます。 アプリ [保護ポリシーを使用するデータ保護フレームワークには、3](https://docs.microsoft.com/mem/intune/apps/app-protection-framework) つのレベルから選択できます。

さらに、Microsoft では、このアプリ保護フレームワークを一連の条件付きアクセスと関連ポリシーで調整しています。すべての組織が開始点として使用することをお勧めします。 この記事のガイダンスを使用して MFA を実装した場合は、その途中です。

モバイル アプリ保護を構成するには、「共通 ID」および「デバイス アクセス ポリシー」 [のガイダンスを使用します](./office-365-security/identity-access-policies.md)。

 1. 「アプリ データ [保護ポリシーの適用」のガイダンスを使用](./office-365-security/identity-access-policies.md#apply-app-data-protection-policies) して、iOS と Android のポリシーを作成します。 ベースライン保護には、レベル 2 (拡張データ保護) をお勧めします。
 2. 承認されたアプリとアプリ保護を [要求する条件付きアクセス ルールを作成します](./office-365-security/identity-access-policies.md#require-approved-apps-and-app-protection)。

## <a name="7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection"></a>7: Intune モバイル アプリ保護を含む、ゲストの MFA と条件付きアクセスを構成する

次に、引き続きゲストと共同作業を行えるのを確認しましょう。 Microsoft 365 E3 プランを使用し、すべてのユーザーに MFA を実装している場合は、設定が必要です。

Microsoft 365 E5 プランを使用している場合に、リスクベースの MFA に Azure Identity Protection を利用している場合は、いくつかの調整を行う必要があります (Azure AD の ID 保護はゲストにまで及ばないので)。

- ゲストと外部ユーザーに対して常に MFA を要求する新しい条件付きアクセス 規則を作成します。
- リスクベースの MFA 条件付きアクセス ルールを更新して、ゲストと外部ユーザーを除外します。

ゲストアクセスと外部[](./office-365-security/identity-access-policies-guest-access.md)アクセスを許可および保護し、ゲスト アクセスが Azure AD でどのように機能し、影響を受けるポリシーを更新するには、共通ポリシーの更新に関するガイダンスを使用します。

作成した Intune モバイル アプリ保護ポリシーと、承認されたアプリとアプリの保護を要求する条件付きアクセスルールは、ゲスト アカウントに適用され、組織のデータの保護に役立ちます。

> [!NOTE]
> 準拠している PC を必要とするために PC をデバイス管理に既に登録している場合は、デバイスコンプライアンスを適用する条件付きアクセス ルールからゲスト アカウントを除外する必要があります。

## <a name="8-enroll-pcs-into-device-management-and-require-compliant-pcs"></a>8: PC をデバイス管理に登録し、準拠した PC を必要とする

従業員のデバイスを登録するには、いくつかの方法があります。 各方法は、デバイスの所有権 (個人または企業)、デバイスの種類 (iOS、Windows、Android)、および管理要件 (リセット、アフィニティ、ロック) に依存します。 これは、並べ替えに少し時間がかかる場合があります。参照: [Microsoft Intune にデバイスを登録します](https://docs.microsoft.com/mem/intune/enrollment/)。

最も簡単に行う方法は [、Windows 10](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)デバイスの自動登録をセットアップすることです。

次のチュートリアルも利用できます。

- [Autopilot を使用して Intune に Windows デバイスを登録する](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [Apple Business Manager (ABM) の Apple の企業デバイス登録機能を使用して、Intune に iOS/iPadOS デバイスを登録する](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

デバイスを登録した後、共通 ID ポリシーとデバイス アクセス ポリシーのガイダンスを使用して [、](./office-365-security/identity-access-policies.md) 次のポリシーを作成します。

- [デバイス コンプライアンス ポリシーの定義](./office-365-security/identity-access-policies.md#define-device-compliance-policies) - Windows 10 の推奨設定には、ウイルス対策保護の要求が含まれます。 Microsoft 365 E5 を使用している場合は、Microsoft Defender for Endpoint を使用して従業員のデバイスの正常性を監視します。 他のオペレーティング システムのコンプライアンス ポリシーに、ウイルス対策保護とエンド ポイント保護ソフトウェアが含まれる必要があります。
- [準拠している PC を必要](./office-365-security/identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets) とする — これは、デバイス コンプライアンス ポリシーを適用する Azure ADの条件付きアクセス ルールです。

デバイスを管理できる組織は 1 つのみなので、Azure AD の条件付きアクセス ルールからゲスト アカウントを除外してください。 デバイスの準拠を必要とするポリシーからゲスト ユーザーと外部ユーザーを除外しない場合、これらのポリシーによってこれらのユーザーがブロックされます。 詳細については、「ゲストアクセスと外部アクセスを許可および保護するための共通ポリシーの更新 [」を参照してください](./office-365-security/identity-access-policies-guest-access.md)。

## <a name="9-optimize-your-network-for-cloud-connectivity"></a>9: クラウド接続用にネットワークを最適化する

従業員の大部分を自宅から仕事に迅速に対応できる場合、このような突然の接続パターンの切り替えは、企業ネットワーク インフラストラクチャに大きな影響を与える可能性があります。 クラウド サービスが導入される前に、多くのネットワークが拡張および設計されました。 多くの場合、ネットワークはリモート ワーカーに対して許容されますが、すべてのユーザーが同時にリモートで使用するように設計されたのではありません。

VPN コンフォレータ、中央ネットワークエグレス機器 (プロキシやデータ損失防止デバイスなど)、中央インターネット帯域幅、バックホール MPLS 回線、NAT 機能などのネットワーク要素は、それらを使用するビジネス全体の負荷が原因で、突然大きな負担になります。 その結果、パフォーマンスと生産性が低下し、在宅勤務に適応しているユーザーのユーザー エクスペリエンスが低下します。

従来、企業ネットワーク経由でトラフィックをルーティングして戻して提供された保護の一部は、ユーザーがアクセスしているクラウド アプリによって提供されます。 この記事のこの手順に達すると、Microsoft 365 のサービスとデータに対して高度なクラウド セキュリティ制御のセットが実装されています。 これらのコントロールを設定すると、リモート ユーザーのトラフィックを直接 365 にルーティングOfficeがあります。 他のアプリケーションにアクセスするために VPN リンクが必要な場合は、スプリット トンネリングを実装することで、パフォーマンスとユーザー エクスペリエンスを大幅に向上させることができます。 組織で合意を得た後、これは、十分に調整されたネットワーク チームが 1 日以内に実現できます。

詳細については、ドキュメントに関する以下のリソースを参照してください。

- [概要: VPN スプリット トンネリングを使用してリモート ユーザーの接続を最適化する](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
- [Office 365 向け VPN スプリット トンネリングの実装](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

このトピックの最近のブログ記事:

- [リモート スタッフのトラフィックをすばやく最適化し、&負荷を軽減する方法](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [セキュリティ担当者と IT 担当者が、今日の独自のリモート ワーク シナリオで最新のセキュリティ制御を実現するための代替手段](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

## <a name="10-train-users"></a>10: ユーザーをトレーニングする

ユーザーのトレーニングによって、ユーザーとセキュリティ運用チームに多くの時間と不満を抱かされる可能性があります。 精通したユーザーは、疑わしい電子メール メッセージで添付ファイルを開く、またはリンクをクリックする可能性が低く、疑わしい Web サイトを回避する可能性が高い。

H phish School [Cybersecurity キャンペーン](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) ハンドブックは、フィッシング攻撃を識別するためのユーザーのトレーニングなど、組織内のセキュリティ認識の強力な文化を確立するための優れたガイダンスを提供します。

Microsoft 365 には、組織内のユーザーに通知するのに役立つ次のリソースが含まれます。

****

|概念|リソース|
|---|---|
|Microsoft 365|[カスタマイズ可能な学習経路](https://docs.microsoft.com/office365/customlearning/) <p>これらのリソースは、組織内のエンド ユーザー向けトレーニングをまとめるのに役立ちます。|
|Microsoft 365 セキュリティ|[学習モジュール: Microsoft 365 の組み込みのインテリジェント なセキュリティで組織を保護する](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>このモジュールでは、Microsoft 365 のセキュリティ機能がどのように機能するのかについて説明し、これらのセキュリティ機能の利点を明確に示します。|
|多要素認証|[2 段階認証: 追加の確認ページとは](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>この記事は、多要素認証の意味と、それが組織で使用されている理由をエンド ユーザーが理解するのに役立ちます。|
|

このガイダンスに加えて、Microsoft では、ユーザーが「アカウントとデバイスをハッカーやマルウェアから保護する」で説明されているアクションを実行 [するようにお勧めします](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)。 それらの操作を次に示します。

- 強力なパスワードの使用
- デバイスの保護
- Windows 10 および Mac PC でセキュリティ機能を有効にする (非管理対象デバイスの場合)

また、次の記事で推奨されるアクションを実行して、ユーザーが個人の電子メール アカウントを保護することもできます。

- [電子メール アカウントOutlook.com保護する](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [2 段階認証による Gmail アカウントの保護](https://go.microsoft.com/fwlink/p/?linkid=2015688)

## <a name="11-get-started-with-microsoft-cloud-app-security"></a>11: Microsoft Cloud App Security の使用を開始する

[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) は、すべてのクラウド サービスでサイバー脅威を特定して対処するための、豊富な可視性、データ移動の制御、高度な分析機能を提供します。 Cloud App Security の使用を開始すると、異常検出ポリシーが自動的に有効になりますが、Cloud App Security の初期学習期間は 7 日間ですが、すべての異常検出アラートが発生する可能性があります。

Cloud App Security の使用を開始します。 後で、より高度な監視と制御を設定できます。

- [クイック スタート: Cloud App Security の使用を開始する](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
- [瞬時の動作分析と異常検出を取得する](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)
- [Microsoft Cloud App Security の詳細](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [新機能を確認する](https://docs.microsoft.com/cloud-app-security/release-notes)
- [基本的なセットアップ手順を参照する](https://docs.microsoft.com/cloud-app-security/general-setup)

## <a name="12-monitor-for-threats-and-take-action"></a>12: 脅威を監視し、アクションを実行する

Microsoft 365 には、状態を監視し、適切なアクションを実行するためのいくつかの方法が含まれています。 最適な開始点は、Microsoft 365 セキュリティ センター ( ) です。このセンターでは、組織の Microsoft セキュア スコア、および注意が必要なアラートやエンティティを [https://security.microsoft.com](https://security.microsoft.com) 表示できます。 [](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)

- [Microsoft 365 セキュリティ センターの使用を開始する](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)
- [レポートを監視し、表示する](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)
- [Microsoft 365 のセキュリティ ポータルを参照する](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="next-steps"></a>次の手順

おめでとうございます。 最も重要なセキュリティ保護の一部をすばやく実装し、組織のセキュリティを強化しました。 これで、脅威保護機能 (Microsoft Defender for Endpoint を含む)、データ分類と保護機能、管理アカウントのセキュリティ保護を行う準備ができました。 Microsoft 365 のセキュリティに関するより詳細で方法に基いた推奨事項については [、Microsoft 365 Security for Business Decision Makers (BDMs)](Microsoft-365-security-for-bdm.md)を参照してください。

また、Microsoft の新しいセキュリティ [センターにアクセス](https://docs.microsoft.com/security)docs.microsoft.com/security。
