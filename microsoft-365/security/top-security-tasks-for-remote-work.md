---
title: 自宅での作業をサポートするセキュリティ チームの上位 12 タスク
f1.keywords:
- CSH
ms.author: bcarter
author: brendacarter
manager: dansimp
audience: Admin
ms.topic: tutorial
ms.prod: m365-security
ms.technology: m365d
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- remotework
ms.custom: admindeeplinkDEFENDER
description: ランサムウェア、フィッシング、悪意のある添付ファイルなど、サイバー脅威からビジネス メールとデータを保護します。
ms.openlocfilehash: 3c3a6ad89a795a45a0f76f868fbc6d23a52b963b
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2022
ms.locfileid: "65319223"
---
# <a name="top-12-tasks-for-security-teams-to-support-working-from-home"></a>自宅での作業をサポートするセキュリティ チームの上位 12 タスク

[Microsoft](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) に似ていて、主に家庭ベースの従業員を突然サポートしている場合は、組織ができるだけ安全に働いているようにお手伝いしたいと考えています。 この記事では、セキュリティ チームが可能な限り迅速に最も重要なセキュリティ機能を実装するのに役立つタスクに優先順位を付けます。

:::image type="content" source="../media/security/security-support-remote-work.png" alt-text="自宅での作業をサポートするために実行する上位のタスク" lightbox="../media/security/security-support-remote-work.png":::


Microsoft のビジネス プランのいずれかを使用している小規模または中規模の組織の場合は、代わりに次のリソースを参照してください。

- [ビジネス プランの Microsoft 365 をセキュリティで保護するためのベスト プラクティス](../admin/security-and-compliance/secure-your-business-data.md)
- [キャンペーンのMicrosoft 365](../business-premium/index.md) (Microsoft 365 Business の推奨されるセキュリティ構成を含む)

エンタープライズ プランを使用しているお客様の場合は、サービス プランに適用される次の表に示すタスクを完了することをお勧めします。 Microsoft 365エンタープライズ プランを購入する代わりに、サブスクリプションを組み合わせる場合は、次の点に注意してください。

- Enterprise Mobility + Security (EMS) E3 と Azure AD P1 が含まれるMicrosoft 365 E3
- EMS E5 と Azure AD P2 が含まれるMicrosoft 365 E5

****

|手順|タスク|すべてのOffice 365 Enterpriseプラン|Microsoft 365 E3|Microsoft 365 E5|
|---|---|---|---|---|
|1|[Azure AD Multi-Factor Authentication (MFA) を有効にする](#1-enable-azure-ad-multi-factor-authentication-mfa)|![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2|[脅威からの保護](#2-protect-against-threats)|![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3|[Microsoft Defender for Office 365を構成する](#3-configure-microsoft-defender-for-office-365)|||![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4|[Microsoft Defender for Identityを構成する](#4-configure-microsoft-defender-for-identity)|||![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5|[Microsoft 365 Defender を有効にする](#5-turn-on-microsoft-365-defender)|||![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6 |[スマートフォンとタブレットIntuneモバイル アプリ保護を構成する](#6-configure-intune-mobile-app-protection-for-phones-and-tablets)||![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7 |[Intuneアプリ保護を含むゲストの MFA と条件付きアクセスを構成する](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)||![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8 |[デバイス管理に PC を登録し、準拠している PC を必要とする](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)||![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9 |[クラウド接続のためにネットワークを最適化する](#9-optimize-your-network-for-cloud-connectivity)|![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10|[ユーザーのトレーニング](#10-train-users)|![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|11|[Microsoft Defender for Cloud Apps の使用を開始する](#11-get-started-with-microsoft-defender-for-cloud-apps)|||![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|12 |[脅威を監視し、アクションを実行する](#12-monitor-for-threats-and-take-action)|![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|![含ま。](../media/d238e041-6854-4a78-9141-049224df0795.png)|

開始する前に、Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">ポータル</a>で[Microsoft 365セキュリティ](./defender/microsoft-secure-score.md)スコアを確認します。 一元化されたダッシュボードから、Microsoft 365 ID、データ、アプリ、デバイス、インフラストラクチャのセキュリティを監視および向上させることができます。 推奨されるセキュリティ機能の構成、セキュリティ関連のタスクの実行 (レポートの表示など)、サード パーティ製のアプリケーションまたはソフトウェアを使用した推奨事項への対処に関するポイントが与えられます。 この記事で推奨されるタスクでは、スコアが上がります。

:::image type="content" source="../media/secure-score.png" alt-text="Microsoft 365 Defender ポータルの Microsoft Secure Score 画面" lightbox="../media/secure-score.png":::

## <a name="1-enable-azure-ad-multi-factor-authentication-mfa"></a>1: Azure AD Multi-Factor Authentication (MFA) を有効にする

自宅で働く従業員のセキュリティを向上させるためにできることは、MFA を有効にすることです。 まだプロセスが整っていない場合は、これを緊急パイロットとして扱い、立ち往生する従業員を支援する準備ができているサポート担当者がいることを確認します。 ハードウェア セキュリティ デバイスを配布できない可能性があるため、Windows Hello生体認証アプリやスマートフォン認証アプリ (Microsoft Authenticator など) を使用します。

通常、MICROSOFT では、MFA を要求する前に、デバイスを Multi-Factor Authentication に登録するために 14 日間ユーザーに提供することをお勧めします。 ただし、従業員が自宅で突然働いている場合は、セキュリティの優先順位として MFA を必要とし、それを必要とするユーザーを支援する準備をしてください。

これらのポリシーの適用には数分かかりますが、今後数日間でユーザーをサポートする準備が整います。

****

|プラン|推奨事項|
|---|---|
|Microsoft 365 プラン (Azure AD P1 または P2 なし)|[Azure AD でセキュリティの既定値を有効にします](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。 Azure AD のセキュリティの既定値には、ユーザーと管理者用の MFA が含まれています。|
|Microsoft 365 E3 (Azure AD P1 を使用)|[一般的な条件付きアクセス ポリシー](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)を使用して、次のポリシーを構成します。 <br/>- [管理者に MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br/>- [すべてのユーザーに MFA を要求する](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br/> - [従来の認証をブロックする](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)|
|Microsoft 365 E5 (Azure AD P2 を使用)|Azure AD Identity Protection を利用して、次のポリシーを作成して、Microsoft [が推奨する条件付きアクセスと関連ポリシーのセット](./office-365-security/identity-access-policies.md) の実装を開始します。<br/> - [サインインのリスクが中、または高のときに MFA を要求する](./office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br/>- [先進認証をサポートしないクライアントはブロックする](./office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)<br/>- [高リスク ユーザーはパスワードを変更する必要がある](./office-365-security/identity-access-policies.md#high-risk-users-must-change-password)|

## <a name="2-protect-against-threats"></a>2: 脅威から保護する

すべてのMicrosoft 365プランには、さまざまな脅威保護機能が含まれています。 これらの機能の保護を強化するには、数分かかります。

- マルウェア対策保護
- 悪意のある URL とファイルからの保護
- フィッシング対策保護
- スパム対策保護

開始点として使用できるガイダンスについては、「[Office 365の脅威から保護](office-365-security/protect-against-threats.md)する」を参照してください。

## <a name="3-configure-microsoft-defender-for-office-365"></a>3: Microsoft Defender for Office 365を構成する

Microsoft 365 E5とOffice 365 E5に含まれるMicrosoft Defender for Office 365は、電子メール メッセージ、リンク (URL)、コラボレーション ツールによってもたらされる悪意のある脅威から組織を保護します。 構成には数時間かかる場合があります。

Microsoft Defender for Office 365:

- 悪意のあるコンテンツの添付ファイルとリンクを検査するインテリジェント システムを使用して、組織を未知の電子メールの脅威からリアルタイムで保護します。 これらの自動化されたシステムには、堅牢な起爆プラットフォーム、ヒューリスティック、機械学習モデルが含まれます。
- チーム サイトやドキュメント ライブラリ内の悪意のあるファイルを特定してブロックすることで、ユーザーがファイルを共同作業して共有するときに組織を保護します。
- 機械学習モデルと高度な偽装検出アルゴリズムを適用して、フィッシング攻撃を回避します。

プランの概要を含む概要については、「[Defender for Office 365](./office-365-security/defender-for-office-365.md)」を参照してください。

グローバル管理者は、次の保護を構成できます。

- [安全なリンク ポリシーを設定する](office-365-security/set-up-safe-links-policies.md)
- [セーフ リンクのグローバル設定を構成する](office-365-security/configure-global-settings-for-safe-links.md)
- [安全な添付ファイル機能のポリシーを設定する](office-365-security/set-up-safe-attachments-policies.md)

これらのワークロードのDefender for Office 365を構成するには、Exchange Online管理者とSharePoint Online 管理者と連携する必要があります。

- [SharePoint、OneDrive、Microsoft TeamsのMicrosoft Defender for Endpoint](office-365-security/mdo-for-spo-odb-and-teams.md)

## <a name="4-configure-microsoft-defender-for-identity"></a>4: Microsoft Defender for Identityを構成する

[Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp) はクラウドベースのセキュリティ ソリューションであり、オンプレミスの Active Directory のシグナルを活用して、組織に対する高度な脅威、ID の漏えい、内部関係者の不正な行動を特定、検出、調査します。 オンプレミスとクラウド インフラストラクチャを保護し、依存関係や前提条件がなく、すぐにメリットを提供できるため、次にこの点に注目してください。

- [Microsoft Defender for Identityクイック スタート](/azure-advanced-threat-protection/install-atp-step1)を参照して、セットアップをすばやく取得する
- ビデオを見る[: Microsoft Defender for Identityの概要](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Microsoft Defender for Identityデプロイの 3 つのフェーズを確認する](/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="5-turn-on-microsoft-365-defender"></a>5: Microsoft 365 Defenderを有効にする

Microsoft Defender for Office 365とMicrosoft Defender for Identityを構成したので、これらの機能の結合されたシグナルを 1 つのダッシュボードで表示できます。 [Microsoft 365 Defender](./defender/microsoft-365-defender.md)は、アラート、インシデント、自動調査と対応、およびワークロード (Microsoft Defender for Identity、Defender for Office 365、Microsoft Defender for Endpoint、およびMicrosoft Defender for Cloud Apps) を<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>の 1 つのウィンドウに挿入します。

:::image type="content" source="../media/top-ten-security-remote-work-mtp-dashboard.png" alt-text="Microsoft 365 Defender ダッシュボード" lightbox="../media/top-ten-security-remote-work-mtp-dashboard.png":::

1 つ以上のDefender for Office 365 サービスを構成したら、MTP を有効にします。 新しい機能は MTP に継続的に追加されます。プレビュー機能の受信をオプトインすることを検討してください。

- [MTP の詳細を確認する](./defender/microsoft-365-defender.md)
- [MTP を有効にする](./defender/m365d-enable.md)
- [プレビュー機能をオプトインする](./defender/preview.md)

## <a name="6-configure-intune-mobile-app-protection-for-phones-and-tablets"></a>6: スマートフォンとタブレットのモバイル アプリ保護Intune構成する

Microsoft Intuneモバイル アプリケーション管理 (MAM) を使用すると、これらのデバイスを管理することなく、スマートフォンやタブレットで組織のデータを管理および保護できます。 次に、動作のしくみを示します。

- デバイス上のどのアプリが管理され、どのような動作が許可されるかを決定する App Protection Policy (APP) を作成します (マネージド アプリのデータが管理されていないアプリにコピーされないようにするなど)。 プラットフォームごとに 1 つのポリシーを作成します (iOS、Android)。
- アプリ保護ポリシーを作成した後、承認されたアプリと APP データ保護を要求する条件付きアクセス規則を Azure AD で作成して、これらを強制します。

APP 保護ポリシーには、多くの設定が含まれます。 さいわい、すべての設定について学習し、オプションを比較検討する必要はありません。 Microsoft では、開始点を推奨することで、設定の構成を簡単に適用できます。 [アプリ保護ポリシーを使用するデータ保護フレームワーク](/mem/intune/apps/app-protection-framework)には、選択できる 3 つのレベルが含まれています。

さらに、Microsoft では、このアプリ保護フレームワークと、すべての組織が開始点として使用することをお勧めする一連の条件付きアクセスと関連ポリシーを調整しています。 この記事のガイダンスを使用して MFA を実装した場合は、道半ばです。

モバイル アプリ保護を構成するには、 [共通 ID およびデバイス アクセス ポリシー](./office-365-security/identity-access-policies.md)のガイダンスを使用します。

 1. [APP データ保護ポリシーの適用に関する](./office-365-security/identity-access-policies.md#apply-app-data-protection-policies)ガイダンスを使用して、iOSとAndroidのポリシーを作成します。 ベースライン保護には、レベル 2 (強化されたデータ保護) をお勧めします。
 2. [承認済みアプリと APP 保護を要求](./office-365-security/identity-access-policies.md#require-approved-apps-and-app-protection)する条件付きアクセス規則を作成します。

## <a name="7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection"></a>7: モバイル アプリ保護を含むゲストの MFA と条件付きアクセスIntune構成する

次に、ゲストと共同作業を続けられるようにしましょう。 Microsoft 365 E3プランを使用していて、すべてのユーザーに対して MFA を実装している場合は、設定されます。

Microsoft 365 E5プランを使用していて、リスクベースの MFA に Azure Identity Protection を利用している場合は、いくつかの調整を行う必要があります (Azure AD Identity Protection はゲストに及ばないため)。

- ゲストと外部ユーザーに対して常に MFA を要求する新しい条件付きアクセス規則を作成します。
- リスク ベースの MFA 条件付きアクセス規則を更新して、ゲストと外部ユーザーを除外します。

[共通ポリシーの更新に関するガイダンスを使用して、ゲストと外部のアクセスを許可および保護](./office-365-security/identity-access-policies-guest-access.md)して、ゲスト アクセスが Azure AD とどのように連携するかを理解し、影響を受けるポリシーを更新します。

作成したIntuneモバイル アプリ保護ポリシーと、承認済みアプリと APP 保護を要求する条件付きアクセス規則がゲスト アカウントに適用され、組織データの保護に役立ちます。

> [!NOTE]
> 準拠している PC を要求するために PC をデバイス管理に既に登録している場合は、デバイスコンプライアンスを強制する条件付きアクセス規則からゲスト アカウントを除外する必要もあります。

## <a name="8-enroll-pcs-into-device-management-and-require-compliant-pcs"></a>8: PC をデバイス管理に登録し、準拠している PC を必要とする

従業員のデバイスを登録するには、いくつかの方法があります。 各方法は、デバイスの所有権 (個人または企業)、デバイスの種類 (iOS、Windows、Android)、および管理要件 (リセット、アフィニティ、ロック) に依存します。 これは、並べ替えに少し時間がかかる場合があります。「[Microsoft Intuneにデバイスを登録](/mem/intune/enrollment/)する」を参照してください。

最も簡単な方法は、[Windows 10 デバイスの自動登録を設定することです](/mem/intune/enrollment/quickstart-setup-auto-enrollment)。

また、次のチュートリアルを利用することもできます。

- [Autopilot を使用してIntuneにWindowsデバイスを登録する](/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [Apple Business Manager (ABM) で Apple の企業デバイス登録機能を使用して、iOS/iPadOS デバイスをIntuneに登録する](/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

デバイスを登録した後、 [共通 ID ポリシーとデバイス アクセス ポリシー](./office-365-security/identity-access-policies.md) のガイダンスを使用して、これらのポリシーを作成します。

- [デバイス コンプライアンス ポリシーを定義](./office-365-security/identity-access-policies.md#define-device-compliance-policies)する - Windows 10の推奨設定には、ウイルス対策の保護が必要です。 Microsoft 365 E5がある場合は、Microsoft Defender for Endpointを使用して従業員のデバイスの正常性を監視します。 他のオペレーティング システムのコンプライアンス ポリシーには、ウイルス対策保護とエンドポイント保護ソフトウェアが含まれていることを確認してください。
- [準拠している PC を必要とする](./office-365-security/identity-access-policies.md#require-compliant-pcs-and-mobile-devices) - これは、デバイス コンプライアンス ポリシーを適用する Azure AD の条件付きアクセス規則です。

デバイスを管理できる組織は 1 つだけです。そのため、Azure AD の条件付きアクセス規則からゲスト アカウントを除外してください。 デバイスコンプライアンスを必要とするポリシーからゲスト ユーザーと外部ユーザーを除外しない場合、これらのポリシーはこれらのユーザーをブロックします。 詳細については、「 [ゲストアクセスと外部アクセスを許可および保護するための一般的なポリシーの更新](./office-365-security/identity-access-policies-guest-access.md)」を参照してください。

## <a name="9-optimize-your-network-for-cloud-connectivity"></a>9: クラウド接続のためにネットワークを最適化する

従業員の大部分を自宅からすぐに使用できるようにする場合、この突然の接続パターンの切り替えは、企業のネットワーク インフラストラクチャに大きな影響を与える可能性があります。 クラウド サービスが導入される前に、多くのネットワークがスケーリングされ、設計されていました。 多くの場合、ネットワークはリモート ワーカーに対して寛容ですが、すべてのユーザーが同時にリモートで使用するようには設計されていませんでした。

VPN コンセントレーター、中央ネットワーク エグレス機器 (プロキシやデータ損失防止デバイスなど)、中央のインターネット帯域幅、バックホールの MPLS 回線、NAT 機能などのネットワーク要素は、それらを使用するビジネス全体の負荷のために突然大きな負担にさらされます。 最終的な結果として、パフォーマンスと生産性が低下し、自宅での作業に適応しているユーザーのユーザー エクスペリエンスが低下します。

従来、企業ネットワーク経由でトラフィックをルーティングすることで提供されていた保護の一部は、ユーザーがアクセスしているクラウド アプリによって提供されます。 この記事でこの手順に到達した場合は、Microsoft 365 サービスとデータに対して高度なクラウド セキュリティ制御のセットを実装しました。 これらの制御を設定すると、リモート ユーザーのトラフィックを直接Office 365にルーティングできる場合があります。 他のアプリケーションへのアクセスに VPN リンクが必要な場合は、分割トンネリングを実装することで、パフォーマンスとユーザー エクスペリエンスを大幅に向上させることができます。 組織で契約を結んだら、1 日以内に適切に調整されたネットワーク チームによってこれを実現できます。

詳細については、Docs の次のリソースを参照してください。

- [概要: VPN 分割トンネリングを使用してリモート ユーザーの接続を最適化する](/Office365/Enterprise/office-365-vpn-split-tunnel)
- [Office 365 向け VPN スプリット トンネリングの実装](/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

このトピックに関する最近のブログ記事:

- [リモート スタッフのトラフィックをすばやく最適化&インフラストラクチャの負荷を軽減する方法](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [今日の一意のリモート作業シナリオで、セキュリティプロフェッショナルと IT が最新のセキュリティ制御を実現するための別の方法](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

## <a name="10-train-users"></a>10: ユーザーをトレーニングする

トレーニング ユーザーは、ユーザーとセキュリティ運用チームに多くの時間とフラストレーションを節約できます。 精通しているユーザーは、疑わしいメール メッセージで添付ファイルを開いたり、リンクをクリックしたりする可能性が低く、疑わしい Web サイトを回避する可能性が高くなります。

「中立大学ケネディ学校 [サイバーセキュリティ キャンペーン の手引き」](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) では、フィッシング攻撃を特定するためのユーザーのトレーニングなど、組織内のセキュリティ意識の強い文化を確立するための優れたガイダンスを提供します。

Microsoft 365には、組織内のユーザーに通知するのに役立つ次のリソースが用意されています。

****

|概念|リソース|
|---|---|
|Microsoft 365|[カスタマイズ可能な学習経路](/office365/customlearning/) <p>これらのリソースは、組織内のエンド ユーザー向けのトレーニングをまとめるのに役立ちます|
|Microsoft 365 セキュリティ|[ラーニング モジュール: 組み込みのインテリジェントなセキュリティで組織をセキュリティで保護Microsoft 365](/learn/modules/security-with-microsoft-365) <p>このモジュールを使用すると、Microsoft 365セキュリティ機能の連携方法を説明し、これらのセキュリティ機能の利点を明確にできます。|
|多要素認証|[2 段階認証: 追加の確認ページは何ですか?](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>この記事は、エンド ユーザーが多要素認証とは何か、組織で使用されている理由を理解するのに役立ちます。|

このガイダンスに加えて、Microsoft では、ユーザーが「 [ハッカーやマルウェアからアカウントとデバイスを保護](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)する」に記載されているアクションを実行することをお勧めします。 それらの操作を次に示します。

- 強力なパスワードを使用する
- デバイスの保護
- Windows 10 PC と Mac PC でセキュリティ機能を有効にする (アンマネージド デバイスの場合)

また、Microsoft では、次の記事で推奨されるアクションを実行して、ユーザーが個人用メール アカウントを保護することをお勧めします。

- [Outlook.com メール アカウントを保護する](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [2 段階認証で Gmail アカウントを保護する](https://go.microsoft.com/fwlink/p/?linkid=2015688)

## <a name="11-get-started-with-microsoft-defender-for-cloud-apps"></a>11: Microsoft Defender for Cloud Appsを使用した概要

[Microsoft Defender for Cloud Apps](/cloud-app-security)は、すべてのクラウド サービスのサイバー脅威を特定して対処するための、豊富な可視性、データ移動の制御、高度な分析を提供します。 Defender for Cloud アプリの使用を開始すると、異常検出ポリシーは自動的に有効になりますが、Defender for Cloud アプリの初期学習期間は 7 日間で、一部の異常検出アラートが発生するわけではありません。

Defender for Cloud アプリで概要できるようになりました。 後で、より高度な監視と制御を設定できます。

- [クイック スタート: Defender for Cloud アプリを使用した概要](/cloud-app-security/getting-started-with-cloud-app-security)
- [瞬時の行動分析と異常検出を取得する](/cloud-app-security/anomaly-detection-policy)
- [Microsoft Defender for Cloud Appsの詳細を確認する](/cloud-app-security/what-is-cloud-app-security)
- [新機能と機能を確認する](/cloud-app-security/release-notes)
- [基本的なセットアップ手順を参照してください](/cloud-app-security/general-setup)

## <a name="12-monitor-for-threats-and-take-action"></a>12: 脅威を監視し、アクションを実行する

Microsoft 365には、状態を監視し、適切なアクションを実行するいくつかの方法が含まれています。 最適な出発点は、組織の [Microsoft Secure Score](./defender/microsoft-secure-score.md) と、注意が必要なアラートまたはエンティティを表示できる<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>です。

- [Microsoft 365 Defender ポータルでの概要](./defender/microsoft-365-defender.md#the-microsoft-365-defender-portal)
- [Microsoft 365のセキュリティ ポータルを表示する](./defender/portals.md)

## <a name="next-steps"></a>次の手順

おめでとうございます! 最も重要なセキュリティ保護の一部を迅速に実装し、組織の安全性が大幅に向上しました。 これで、脅威保護機能 (Microsoft Defender for Endpointを含む)、データの分類と保護機能、管理アカウントのセキュリティ保護をさらに進める準備が整いました。 Microsoft 365に関するより詳細で組織的な一連のセキュリティに関する推奨事項については、「[ビジネス意思決定者向けセキュリティ (BDMs)のMicrosoft 365」を](Microsoft-365-security-for-bdm.md)参照してください。

また、docs.microsoft.com/security に関する Microsoft の新しい[Defender for Cloud](/security)もご覧ください。
