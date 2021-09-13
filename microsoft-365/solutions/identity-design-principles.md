---
title: Microsoft 365リソース計画 - セキュリティ アーキテクチャ
description: Microsoft のテクニカル プリンシパル アーキテクトである Alex Shteynberg の Microsoft Enterpriseアーキテクチャのトップ デザイン戦略について説明します。
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: 6d0599d11dd5892b032bda1285b92fbc8a09354b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214173"
---
# <a name="to-identity-and-beyondone-architects-viewpoint"></a>ID とそれ以降の 1 つのアーキテクトの視点

この記事では、Microsoft のプリンシパル テクニカル アーキテクトである[Alex Shteynberg](https://www.linkedin.com/in/alex-shteynberg/)が、Microsoft 365および他の Microsoft クラウド サービスを採用しているエンタープライズ組織のトップ デザイン戦略について説明します。

## <a name="about-the-author"></a>筆者について

![Alex Shteynberg 写真。](../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg)

ニューヨーク Microsoft テクノロジ センターのプリンシパル テクニカル アーキテ [クトです](https://www.microsoft.com/mtc?rtc=1)。 主に大規模な顧客と複雑な要件を扱っています。 私の視点と意見は、これらの相互作用に基づいており、すべての状況に適用されるとは言い得ない。 しかし、私の経験では、最も複雑な課題でお客様を支援できる場合は、すべての顧客を支援できます。

通常、毎年 100 人を超える顧客と仕事をしています。 すべての組織に固有の特性がある一方で、傾向や共通点を確認するのも興味深い点です。 たとえば、1 つの傾向は、多くの顧客に対する業界間の関心です。 結局のところ、銀行の支店には、コーヒーショップとコミュニティ センターもあります。

私の役割では、お客様が独自の一連のビジネス目標に対処するために、最高の技術的ソリューションに到着するのを支援する点に重点を置きます。 正式には、ID、セキュリティ、プライバシー、コンプライアンスに重点を置いて取り組む。 私は、これらのタッチすべてが私たちが行うという事実が大好き。 これは、ほとんどのプロジェクトに関わる機会を与えます。 これにより、非常に忙しく、この役割を楽しみます。

私はニューヨーク市に住んでいて(最高です!)、その文化、食べ物、人々の多様性を本当に楽しんでいる(トラフィックではありません)。 私はできるとき旅行を愛し、私の一生の間に世界のほとんどを見るのを望む。 現在、野生動物について学ぶためにアフリカへの旅行を研究しています。

## <a name="guiding-principles"></a>ガイドの原則

- **多くの場合、** シンプルな方が優れた方法です。テクノロジを使って何でも実行できますが、そうする必要があるという意味ではありません。 特にセキュリティ領域では、多くのお客様がソリューションをオーバーエンジナーします。 この点 [を強調するために](https://www.youtube.com/watch?v=SOQgABDSYZE) 、Google の Stripe 会議のこのビデオが好きです。
- **人、プロセス、テクノロジ**: [最初に技術ではなく](https://en.wikipedia.org/wiki/Human-centered_design) 、プロセスを強化するユーザー向け設計。 "完全な" ソリューションはありません。 さまざまなリスク要因のバランスを取る必要があります。ビジネスごとに決定が異なります。 ユーザーが後で避けるアプローチを設計する顧客が多すぎます。
- **最初に 「なぜ」、後で 「方法**」に焦点を当てる: 100万の質問を持つ迷惑な 7-yr 古い子供になります。 正しい質問が分からない場合は、正しい回答を得る必要があります。 多くの顧客は、ビジネス上の問題を定義する代わりに、物事がどのように機能する必要があるのかについて仮定しています。 実行できるパスは常に複数です。
- **過去のベスト プラクティスの長い尾**: ベスト プラクティスが軽い速度で変化することを認識します。 3 か月以上前に Azure ADを見た場合は、現在の日付が更新されている可能性があります。 ここに記載されている内容はすべて、公開後に変更される場合があります。 今日の "ベスト" オプションは、今から 6 か月後に同じではない可能性があります。

## <a name="baseline-concepts"></a>ベースラインの概念

このセクションをスキップしない。 多くの場合、クラウド サービスを何年も使用しているお客様に対しても、これらのトピックに一歩下がらなければならないと思います。
悲しいかな、言語は正確なツールではない。 多くの場合、同じ単語を使用して、異なる概念や異なる単語を意味し、同じ概念を意味します。 以下の図を使用して、いくつかのベースライン用語と "階層モデル" を確立します。
<br><br>

![テナント、サブスクリプション、サービス、およびデータの図。](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)

<br>

あなたが泳ぐことを学ぶとき、それは海の真ん中ではなく、プールで始める方が良いです。 この図で技術的に正確にしようとはしていない。 基本的な概念について説明するモデルです。

図の説明

- テナント = Azure サーバーのインスタンスAD。 これは、階層の "トップ"、または図のレベル 1 です。 これは、他のすべてが発生する["境界](/azure/active-directory/users-groups-roles/licensing-directory-independence)" と見なされます (Azure AD[B2B](/azure/active-directory/b2b/what-is-b2b) は別です)。 すべての Microsoft エンタープライズ クラウド サービスは、これらのテナントの 1 つの一部です。 コンシューマー サービスは別個です。 "Tenant" は、ドキュメントOffice 365 Azure テナント、WVD テナントなどとして表示されます。 多くの場合、これらのバリエーションは、顧客に混乱を引き起こします。
- 図のレベル 2 であるサービス/サブスクリプションは、1 つのテナントにのみ属します。 ほとんどの SaaS サービスは 1:1 であり、移行なしでは移動できない。 Azure は異なるので、課金 [や](/azure/cost-management-billing/manage/billing-subscription-transfer) サブスクリプションを別の [テナント](/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) に移動できます。 Azure サブスクリプションを移動する必要があるお客様は多数います。 これにはさまざまな意味があります。 サブスクリプションの外部に存在するオブジェクトは移動しません (役割ベースのアクセス制御、Azure RBAC、グループ、アプリ、ポリシーなどの Azure AD オブジェクトなど)。 また、一部のサービス (Azure Key Vault、Data Bricks など)。 ビジネス上の必要のないサービスを移行しない。 移行に役立つ一部のスクリプトは[、GitHub。](https://github.com/lwajswaj/azure-tenant-migration)
- 特定のサービスには、通常、何らかの種類の "サブレベル" 境界、またはレベル 3 (L3) があります。 これは、セキュリティ、ポリシー、ガバナンスの分離などについて理解する場合に役立ちます。 残念ながら、私が知っている統一された名前はありません。 L3 の名前の例としては、Azure Subscription = [resource があります](/azure/azure-resource-manager/management/manage-resources-portal)。Dynamics 365 CE =[インスタンス](/dynamics365/admin/new-instance-management);Power BI =[ワークスペース](/power-bi/service-create-the-new-workspaces);Power Apps =[環境](/power-platform/admin/environments-overview);などなど。
- レベル 4 は、実際のデータが保存されている場所です。 この 「データ プレーン」は複雑なトピックです。 一部のサービスは、RBAC AD Azure AD使用しています。他のサービスは使用しない場合があります。 委任に関するトピックが表示される場合は、少し説明します。

多くのお客様 (および Microsoft の従業員) が混乱したり、次のような質問がある場合は、いくつかの追加概念を見つける必要があります。

- 誰でも [、多](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) くのテナントをコスト [無しで作成できます](https://azure.microsoft.com/pricing/details/active-directory/)。 その中でプロビジョニングされたサービスは必要ない。 私は数十を持っています。 各テナント名は、Microsoft のワールドワイド クラウド サービスで一意です (つまり、同じ名前を持つテナントは 2 つはありません)。 これらはすべて、次の形式 TenantName.onmicrosoft.com。 テナントを自動的に作成するプロセス (管理されていないテナント)[も用意されています](/azure/active-directory/users-groups-roles/directory-self-service-signup)。 たとえば、ユーザーが他のテナントに存在しない電子メール ドメインを使用してエンタープライズ サービスに登録すると、この問題が発生することがあります。
- 管理テナントでは、多くの [DNS ドメイン](/azure/active-directory/fundamentals/add-custom-domain) をそのテナントに登録できます。 これにより、元のテナント名は変更されません。 現在、テナントの名前を変更する簡単な方法はありません (移行以外)。 最近ではテナント名は技術的に重要ではありませんが、これを制限している場合があります。
- サービスの展開をまだ計画していない場合でも、組織のテナント名を予約する必要があります。 それ以外の場合、誰かがあなたからそれを取り出し、それを取り戻す簡単なプロセスはありません (DNS 名と同じ問題)。 この方法は、お客様から頻繁に聞き取ります。 テナント名の内容は、議論のトピックです。
- DNS 名前空間を所有している場合は、テナントにこれらすべての名前空間を追加する必要があります。 それ以外の場合は、[](/azure/active-directory/users-groups-roles/directory-self-service-signup)この名前の管理されていないテナントを作成し、そのテナントを管理[するために中断を引き起こす可能性があります](/azure/active-directory/users-groups-roles/domains-admin-takeover)。
- DNS 名前空間 (contoso.com など) は、1 つのテナントにのみ属できます。 これは、さまざまなシナリオ (たとえば、合併または買収中に電子メール ドメインを共有するなど) に影響を与えます。 別のテナントに DNS サブ (div.contoso.com など) を登録する方法がありますが、これは避ける必要があります。 トップ レベルのドメイン名を登録すると、すべてのサブドメインが同じテナントに属すると見なされます。 マルチテナントのシナリオ (以下を参照) では、通常、別のトップ レベルのドメイン名 (contoso.ch や ch-contoso.com など) を使用することをお勧めします。
- Whoテナントを "所有" する必要がありますか? テナントを現在所有しているユーザーを知らないお客様はよく見かけ取ります。 これは大きな赤いフラグです。 Microsoft サポートを ASAP に呼び出します。 同じ問題は、サービス所有者 (多くの場合、管理者Exchange) がテナントの管理に指定されている場合です。 テナントには、将来必要なすべてのサービスが含まれる可能性があります。 テナントの所有者は、組織内のすべてのクラウド サービスの有効化を決定できるグループである必要があります。 もう 1 つの問題は、テナント所有者グループに対してすべてのサービスの管理を求める場合です。 これは大規模な組織では拡大縮小は行わない。
- サブ/スーパー テナントの概念はありません。 何らかの理由で、この神話は繰り返し続ける。 これは [、Azure AD B2C](/azure/active-directory-b2c/) テナントにも適用されます。 「自分の B2C 環境が XYZ テナントにある」、または「Azure テナントを自分のテナントに移動する方法Office 365です。
- このドキュメントでは、ほとんどのお客様が使用している商用の世界規模のクラウドに主に焦点を当てています。 ソブリン クラウドについて知って [便利な場合があります](/azure/active-directory/develop/authentication-national-cloud)。 ソブリン クラウドには、この議論の対象範囲を超えるものについて議論する追加の意味があります。

## <a name="baseline-identity-topics"></a>ベースライン ID のトピック

Microsoft の ID プラットフォーム (Azure Azure Active Directory) に関する多くのAD。 始め始めつ間近の人には、多くの場合、圧倒的な気持ちになります。 そのことを学んだ後も、常に革新と変化に取り組むのは難しい場合があります。 顧客とのやり取りでは、多くの場合、ビジネス目標と、これらに対処するための "Good, Better, Best" アプローチ (およびこれらのトピックの人間の "崖のメモ") の間の "翻訳者" として機能しています。 完璧な答えはめったに見当たりませんが、"正しい" 決定はさまざまなリスク要因のバランスです。 以下は、お客様と話し合う傾向がある一般的な質問と混乱の分野の一部です。

### <a name="provisioning"></a>プロビジョニング

Azure ADは、ID の世界におけるガバナンスの欠如を解決しません。 [ID ガバナンスは](/azure/active-directory/governance/identity-governance-overview) 、クラウド上の決定に依存しない重要な要素である必要があります。 ガバナンス要件は時間の間に変化します。これは、プログラムであり、ツールではない理由です。

[Azure AD Connect](/azure/active-directory/hybrid/whatis-azure-ad-connect)[対Microsoft Identity Manager](/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) vs. 何か他の (サード パーティまたはカスタム) か。 今も将来も多くの頭痛を自分で保存し、Azure AD Connect。 このツールには、顧客特有の構成や継続的な技術革新に対処するためのあらゆる種類のスマートがあります。

より複雑なアーキテクチャに向かって動く可能性のあるいくつかのエッジ ケース:

- これらの間にネットワークADのない複数のフォレストがあります。 クラウド プロビジョニングという新しい [オプションがあります](/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning)。
- Active Directory もインストールする必要もありません。 Azure AD Connect LDAP から同期するように構成できます[(パートナー](/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison)が必要な場合があります)。
- 同じオブジェクトを複数のテナントにプロビジョニングする必要があります。 これは技術的にはサポートされていませんが、"same" の定義に依存します。

既定の同期ルール (フィルター オブジェクト、[属性](/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering)[の変更](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)、[代替ログイン ID](/azure/active-directory/hybrid/plan-connect-userprincipalname)など) をカスタマイズする必要がありますか。 それを避ける! ID プラットフォームは、それを使用するサービスと同じ価値があります。 あらゆる種類の構成を行えますが、この質問に答えるには、アプリケーションへの影響を確認する必要があります。 メールが有効なオブジェクトをフィルター処理すると、オンライン サービスの GAL は不完全になります。アプリケーションが特定の属性に依存している場合、これらをフィルター処理すると予期しない影響を受け取る可能性があります。などなど。 ID チームの決定ではありません。

XYZ SaaS は Just-in-Time (JIT) プロビジョニングをサポートしています。なぜ同期が必要なのですか? 上記を参照してください。 多くのアプリケーションでは、機能の "プロファイル" 情報が必要です。 メールが有効なすべてのオブジェクトが使用できない場合は、GAL を使用できません。 Azure アプリケーションと統合 [されたアプリケーションでの](/azure/active-directory/app-provisioning/user-provisioning) ユーザー プロビジョニングにも同様AD。

### <a name="authentication"></a>認証

[パスワード ハッシュ同期](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) (PHS) とパススルー [認証](/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (PTA) vs. [フェデレーション](/azure/active-directory/hybrid/how-to-connect-fed-compatibility)。

通常、フェデレーションに関する熱心 [な議論](/azure/active-directory/hybrid/choose-ad-authn) があります。 単純な方が通常は優れた方法なので、そうしない理由がない限り PHS を使用します。 また、同じテナント内の DNS ドメインごとに異なる認証方法を構成できます。

一部のお客様は、主に次の場合にフェデレーション + PHS を有効にしています。

- フェデレーション サービス [が利用できない](/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) 場合に (障害復旧の場合) に戻るオプション。
- その他の機能 (例: [Azure AD DS)](/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)とセキュリティ サービス (例: 漏洩 [した資格情報](/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials))
- フェデレーション認証を理解していない Azure のサービス [(Azure Files](/azure/storage/files/storage-files-active-directory-overview)など) のサポート。

多くの場合、クライアント認証フローを通じて顧客を見て、誤解を明確にします。 結果は下の図のようになります。これは、そこに行く対話的なプロセスほど良くはない。

![ホワイトボードの会話の例。](../media/solutions-architecture-center/identity-beyond-whiteboard-example.png)

この種類のホワイトボード図面は、認証要求のフロー内でセキュリティ ポリシーが適用される場所を示しています。 この例では、Active Directory フェデレーション サービス (AD FS) を通じて適用されるポリシーは、最初のサービス要求には適用されますが、それ以降のサービス要求には適用されません。 これは、セキュリティコントロールを可能な限りクラウドに移動する少なくとも 1 つの理由です。

覚えている限り、シングル サインオン [(SSO)](/azure/active-directory/manage-apps/what-is-single-sign-on) の夢を追い続け続け続け、 一部のお客様は、"正しい" フェデレーション (STS) プロバイダーを選択することでこれを実現できると考えています。 Azure ADは SSO 機能を有効 [にするのに](/azure/active-directory/manage-apps/plan-sso-deployment) 大きく役立ちますが、STS は魔法にかなっています。 重要なアプリケーションで使用される"レガシ" 認証方法が多すぎます。 パートナー ソリューションで Azure AD [を拡張すると、](/azure/active-directory/saas-apps/tutorial-list) これらの多くのシナリオに対処できます。 SSO は戦略とジャーニーです。 アプリケーションの標準に進む必要がない [場合は、そこに行く必要があります](/azure/active-directory/develop/v2-app-types)。 このトピックに関連する方法は、[](/azure/active-directory/authentication/concept-authentication-passwordless)パスワードレス認証への道のりで、魔法のような答えはありません。

[多要素認証](/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) は今日不可欠です ([詳細については、こちらを](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) 参照)。 ユーザーの行動 [分析に追加](/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) すると、最も一般的なサイバー攻撃を防止するソリューションが用意されています。 コンシューマー サービスでさえ、MFA が必要に移行しています。 それでも、最新の認証アプローチに移行したくない多くの顧客と [まだ会](../enterprise/hybrid-modern-auth-overview.md) っています。 私が聞く最大の引数は、ユーザーと従来のアプリケーションに影響を与えるという話です。 場合によっては、お客様が変更を発表した場合、お客様Exchange Online[役立つ場合があります](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282)。 多くの Azure AD [レポートが](/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) 、この移行のお客様を支援するために利用できます。

### <a name="authorization"></a>Authorization

Wikipedia [ごとに、"](https://en.wikipedia.org/wiki/Authorization)承認する" のは、アクセス ポリシーを定義する方法です。 多くのユーザーは、オブジェクト (ファイル、サービスなど) へのアクセス制御を定義する機能と見なします。 現在のサイバー脅威の世界では、この概念は、さまざまな脅威ベクトルに対応し、それに応じてアクセス制御をすばやく調整できる動的ポリシーに急速に進化しています。 たとえば、異常な場所から銀行口座にアクセスすると、追加の確認手順が表示されます。 この点に取り組むには、ポリシー自体だけでなく、脅威検出とシグナル相関の手法のエコシステムも考慮する必要があります。

Azure ADのポリシー エンジンは、条件付き [アクセス ポリシーを使用して実装されます](/azure/active-directory/conditional-access/overview)。 このシステムは、動的な意思決定を行うさまざまな他の脅威検出システムからの情報に依存します。 単純なビューは、次の図のようになります。

![Azure のポリシー エンジンAD。](../media/solutions-architecture-center/identity-and-beyond-illustration-3.png)

これらすべての信号を組み合わせることで、次のような動的ポリシーが可能です。

- デバイスで脅威が検出された場合、データへのアクセスは、ダウンロードすることなく Web にのみ減少します。
- 異常に多くのデータをダウンロードしている場合、ダウンロードしたデータは暗号化され制限されます。
- 管理されていないデバイスからサービスにアクセスすると、機密性の高いデータからブロックされますが、制限されていないデータにはアクセスできますが、別の場所にコピーする機能はありません。

この拡張された承認定義に同意する場合は、追加のソリューションを実装する必要があります。 実装するソリューションは、ポリシーを動的に設定する方法と、優先度を設定する脅威によって異なります。 このようなシステムの例を次に示します。

- [Azure AD Identity Protection](/azure/active-directory/identity-protection/)
- [Microsoft Defender for Identity](/azure-advanced-threat-protection/)
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md)
- [Microsoft Cloud App Security](/cloud-app-security/) (MCAS)
- [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md)
- [Microsoft Intune](/mem/intune/)
- [Microsoft Information Protection](../compliance/information-protection.md) (MIP)
- [Azure Sentinel](/azure/sentinel/)

もちろん、Azure ADに加えて、さまざまなサービスやアプリケーションには独自の承認モデルがあります。 これらのいくつかについては、後の「委任」セクションで説明します。

### <a name="audit"></a>監査

Azure ADには、詳細 [な監査およびレポート機能](/azure/active-directory/reports-monitoring/) があります。 ただし、セキュリティ上の意思決定に必要な情報のソースは、通常はこれが唯一ではありません。 詳細については、「委任」セクションをご覧ください。

## <a name="theres-no-exchange"></a>何もExchange

焦らないで下さい！ これは、非推奨Exchange (またはSharePointなど) を意味する意味ではありません。 これは依然としてコア サービスです。 つまり、今はかなり長い間、テクノロジ プロバイダーはユーザー エクスペリエンス (UX) を複数のサービスのコンポーネントに移行しています。 このMicrosoft 365例は、「モダンな添付ファイル」です[](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)。電子メールの添付ファイルは、オンラインまたは電子メールのSharePointにOneDrive for Business。

![メールにファイルを添付する。](../media/solutions-architecture-center/modern-attachments.png)

このクライアントOutlook見て、このエクスペリエンスの一部として"接続" されている多くのサービスを確認Exchange。 これには、Azure AD、Microsoft Search、アプリ、プロファイル、コンプライアンス、およびグループOffice 365含まれます。

![Outlook吹き出し付きインターフェイス。](../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png)

今後の機能[Microsoft 流動フレームワーク](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268)プレビューの詳細については、この記事を参照してください。 プレビューで、会話の読み取りと返信をTeamsで直接Outlook。 実際、クライアント[Teams、](https://products.office.com/microsoft-teams/download-app)この戦略のより顕著な例の 1 つです。

全体的に、Microsoft クラウド内のサービスとサービスの間に明確Office 365線を引くのは難しくなってきている。 1 つのコンポーネントを使用する場合でも、すべての機能に対して完全なイノベーションの恩恵を受け、お客様にとって大きなメリットと見なしています。 かなりクールで、多くのお客様に大きな影響を与えています。

今日、多くのお客様の IT グループが"製品" を中心に構成されているのが分かっています。 特定の製品ごとに専門家が必要なので、オンプレミスの世界では論理的です。 しかし、これらのサービスがクラウドに移行する中で、Active Directory データベースや Exchange データベースをデバッグする必要が全くなかったのは、本当に嬉しく思います。 オートメーション (クラウドの種類) は、特定の反復的な手動ジョブを削除します (工場に何が起こったかを確認します)。 ただし、これらは、サービス間のやり取り、影響、ビジネス ニーズなどについて理解するために、より複雑な要件に置き換えられる。 学習する必要がある場合 [は](/learn/)、クラウド変換によって有効な大きな機会があります。 テクノロジに飛び込む前に、IT スキルやチーム構造の変化を管理する方法について、お客様とよく話をします。

すべてのユーザー SharePoint開発者に対して、「オンラインで XYZ を実行する方法SharePointしてください。 ワークフロー [Power Automate](/power-automate/) (またはFlow) を使用すると、はるかに強力なプラットフォームになります。 [Azure Bot Framework を使用](/azure/bot-service/)して、500-K アイテム リストの優れた UX を作成します。 CSOM ではなく[microsoft Graph](https://developer.microsoft.com/graph/)の使用を開始します。 [Microsoft Teams](/MicrosoftTeams/Teams-overview)にはSharePoint世界も含まれます。 リストできる他にも多くの例があります。 そこには広大で素晴らしい宇宙があります。 ドアを開き、 [探索を開始します]()。

もう 1 つの一般的な影響は、コンプライアンス領域です。 このクロスサービスアプローチは、多くのコンプライアンス ポリシーを完全に混同しているようです。 「すべての電子メール通信を電子情報開示システムにジャーナル処理する必要がある」という組織が表示されます。 電子メールがメールではなく、他のサービスへのウィンドウである場合、これは本当に何を意味しますか? Office 365の包括的なアプローチがありますが、人や[](../compliance/index.yml)プロセスの変化は、多くの場合、テクノロジよりもはるかに困難です。

他にも多くの人とプロセスへの影響があります。 私の意見では、これは重要で議論の少ない領域です。 おそらく、別の記事でもっと詳しい。

## <a name="tenant-structure-options"></a>テナント構造のオプション

### <a name="single-tenant-vs-multi-tenant"></a>単一テナントとマルチテナント

一般に、ほとんどのお客様は 1 つの実稼働テナントのみを使用する必要があります。 複数のテナントが難しい (検索を行う) 多くのBing理由や、[この](https://www.bing.com/search?q=office%20365%20multiple%20tenants)ホワイトペーパーを[読み取る必要があります](https://aka.ms/multi-tenant-user)。 同時に、私が一緒に働く多くのエンタープライズ顧客には、IT 学習、テスト、実験用の別の (小規模) テナントがあります。 Azure ライトハウスを使用すると、テナント間の Azure アクセス [が容易になります](https://azure.microsoft.com/services/azure-lighthouse/)。 Office 365その他の多くの SaaS サービスには、テナント間のシナリオに制限があります。 Azure の [B2B シナリオでは、AD検討する必要](/azure/active-directory/b2b/what-is-b2b) があります。

多くのお客様は、合併および買収 (M&A) の後に複数の生産テナントを終了し、統合を行う必要があります。 今日は単純ではなく、Microsoft Consulting Services (MCS) またはパートナーとサード パーティ製ソフトウェアが必要です。 今後、マルチテナントのお客様とのさまざまなシナリオに対応するエンジニアリング作業が進行中です。

一部の顧客は、複数のテナントと一緒に行く選択をします。 これは非常に慎重な決定であり、ほとんど常にビジネス上の理由が駆動される必要があります。 いくつかの例には、次のようなものがあります。

- 異なるエンティティ間の簡単なコラボレーションが必要ではなく、強力な管理および他の分離のニーズがある保持型の会社構造。
- 買収後、2 つのエンティティを分離するビジネス上の決定が行われた。
- 顧客の実稼働環境を変更しない、お客様の環境のシミュレーション。
- お客様向けソフトウェアの開発。

これらのマルチテナントシナリオでは、多くの場合、テナント間で構成を同じにするか、構成の変更とドリフトについて報告する必要があります。 これは、多くの場合、手動による変更からコードとしての構成への移行を意味します。 Microsoft Premiere サポートは、このパブリック IP に基づいて、これらの種類の要件に関するワークショップを提供します <https://Microsoft365dsc.com> 。

### <a name="multi-geo"></a>Multi-Geo

複数 [地域または複数](../enterprise/microsoft-365-multi-geo.md) 地域にしない場合は、それが問題です。 複数Office 365を使用すると、データ常駐の要件を満たすために選択した地域の場所に保存されているデータをプロビジョニング[および保存できます](../enterprise/o365-data-locations.md)。 この機能には多くの誤解があります。 以下の点にご注意ください。

- パフォーマンス上の利点を提供する必要はない。 ネットワーク設計が正しく設定されていないと、 [パフォーマンスが](https://aka.ms/office365networking) 低下する可能性があります。 必ずしもデータではなく、Microsoft ネットワークにデバイスを "閉じる" 方法で取得します。
- GDPR 準拠の [ソリューションではありません](https://www.microsoft.com/trust-center/privacy/gdpr-overview)。 GDPR は、データ主権やストレージの場所に焦点を当てない。 その他のコンプライアンス フレームワークがあります。
- 管理の委任 (以下を参照) や情報バリア [は解決しません](../compliance/information-barriers.md)。
- マルチテナントと同じではなく、追加のユーザー プロビジョニング [ワークフローが](https://github.com/MicrosoftDocs/azure-docs-pr/blob/master/articles/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation.md) 必要です。
- テナント [(Azure アカウント)](../enterprise/moving-data-to-new-datacenter-geos.md) を別ADに移動する必要があります。

## <a name="delegation-of-administration"></a>管理の委任

ほとんどの大規模な組織では、職務と役割ベースのアクセス制御 (RBAC) の分離が必要な現実です。 私は前もって謝るつもりです。 これは、一部の顧客が望むほど簡単ではありません。 顧客、法律、コンプライアンス、その他の要件は異なっています。また、世界中で競合する場合があります。 シンプルさと柔軟性は、多くの場合、互いに反対側に位置します。 私を間違え、これでより良い仕事をすることができます。 時間の長い間、大幅な改善が行なっています(今後も)。 379230 ドキュメントを読むことなく、ビジネス要件に合ったモデルを作成するには、お近くの [Microsoft](https://www.microsoft.com/mtc) テクノロジ センターにアクセスしてください。 ここでは、あなたが考えるべきものに焦点を当て、なぜそれがこの方法なのかに焦点を当てる必要はありません。 以下は、計画する 5 つの異なる領域と、私が遭遇した一般的な質問の一部です。

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Azure ADおよびMicrosoft 365管理センター

組み込みの役割の長く成長 [しているリストがあります](/azure/active-directory/roles/permissions-reference)。 各役割は、特定のアクションを実行するためにグループ化された役割のアクセス許可の一覧で構成されます。 これらのアクセス許可は、各ロール内の [説明] タブで確認できます。 または、これらのより人間が読み取り可能なバージョンを、Microsoft 365 管理できます。 組み込みロールの定義は変更できません。 一般的に、これらを 3 つのカテゴリにグループ化します。

- **グローバル管理者**: この "すべての強力な"[](../enterprise/protect-your-global-administrator-accounts.md)役割は、他のシステムと同様に高度に保護する必要があります。 一般的な推奨事項には、永続的な割り当てなしと Azure AD Privileged Identity Management (PIM) の使用が含まれます。強力な認証。などなど。 興味深いことに、この役割は既定ではすべてのアクセス権を与えるという意味ではないものです。 通常、コンプライアンス アクセスと Azure アクセスについては、後で説明します。 ただし、この役割では、テナント内の他のサービスへのアクセスを常に割り当てできます。
- **特定のサービス** 管理者: 一部のサービス (Exchange、SharePoint、Power BI など) は、Azure AD から高レベルの管理役割を使用します。 これは、すべてのサービスで一貫しているのではないし、後で説明するサービス固有の役割が多い。
- **機能**: 特定の操作 (ゲスト招待者など) に焦点を当てたロールの長い (および成長している) リストがあります。 定期的に、これらの多くが顧客のニーズに基づいて追加されます。

すべてを委任できません (ただし、ギャップは減少しています)、グローバル管理者の役割を使用する必要がある場合があります。 コードとしての構成と自動化は、この役割のユーザー メンバーシップではなく考慮する必要があります。

**注**: このMicrosoft 365 管理センターインターフェイスはユーザーフレンドリーですが、Azure 管理者エクスペリエンスと比較して機能のサブセットADがあります。 どちらのポータルも同じ Azure ADロールを使用します。そのため、変更は同じ場所で行っています。 ヒント: すべての Azure を煩雑にせずに ID 管理に重点を置いて管理 UI を使用する場合は、 を使用します <https://aad.portal.azure.com> 。

名前には何がありますか? 役割の名前を前提としない。 言語は非常に正確なツールではありません。 目標は、必要な役割を確認する前に委任する必要がある操作を定義する必要があります。 "Security Reader" ロールに誰かを追加しても、すべてのユーザーにセキュリティ設定が表示されるという問題はありません。

カスタム ロールを作成 [する機能は](/azure/active-directory/users-groups-roles/roles-custom-overview) 、一般的な質問です。 これは、現在の Azure AD制限されますが (以下を参照)、時間の間に機能が拡大します。 これらは Azure AD の関数に適用できると考え、階層モデル (上記で説明) にまたがって "ダウン" できない可能性があります。 "カスタム" を扱うたびに、"simple is better" のプリンシパルに戻る傾向があります。

もう 1 つの一般的な質問は、役割をディレクトリのサブセットにスコープ設定する機能です。 1 つの例は、「EU のユーザー専用のヘルプデスク管理者」のようなものです。 [管理単位](/azure/active-directory/users-groups-roles/directory-administrative-units) (AU) は、この問題に対処することを目的とします。 上記と同様に、これらの機能は Azure ADに適用され、"down" に及びない可能性があります。 もちろん、特定の役割はスコープ (グローバル管理者、サービス管理者など) には意味がありません。

今日では、これらのすべてのロールに直接メンバーシップ (または Azure の PIM を使用する場合は動的割 [り当て) がADされています](/azure/active-directory/privileged-identity-management/)。 つまり、お客様は Azure ADでこれらを直接管理する必要があります。これらはセキュリティ グループ のメンバーシップに基づくものにすることはできません。 昇格された権限で実行する必要がある場合、これらを管理するためのスクリプトを作成するファンではありません。 一般に、ServiceNow のようなプロセス システムとの API 統合や、Saviynt のようなパートナー ガバナンス ツールの使用をお勧めします。 この問題に時間の間に取り組むエンジニアリング作業が行なっています。

Azure AD [PIM について](/azure/active-directory/privileged-identity-management/) 何度か説明しました。 オンプレミスコントロールに対応Microsoft Identity Manager (MIM) 特権アクセス[管理](/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services)(PAM) ソリューションがあります。 また、Privileged Access [Workstations](/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) と [Azure ADを参照してください](/azure/active-directory/governance/identity-governance-overview)。 また、さまざまなサード パーティ製ツールもあります。このツールを使用すると、Just-in-time、Just-enough、および動的な役割昇格を有効にできます。 これは通常、環境を保護するためのより大きな議論の一部です。

場合によっては、外部ユーザーを役割に追加するシナリオが呼び出される場合があります (上記の「マルチテナント」セクションを参照)。 これはうまく動作します。 [Azure AD B2B は](/azure/active-directory/b2b/) 、おそらく別の記事で、顧客を説明する大きな楽しいトピックです。

### <a name="security-and-compliance-center-scc"></a>セキュリティおよびコンプライアンス センター (SCC)

[Office 365 セキュリティ](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)& コンプライアンス センターのアクセス許可は、Azure の役割とは別の "役割グループ" のADです。 これらの役割グループの中には、Azure AD ロール (セキュリティ リーダーなど) と同じ名前を持ち、異なるメンバーシップを持つ場合があります。 Azure の役割を使用ADします。 各役割グループは、1 つ以上の "ロール" (同じ単語を再利用する方法を参照してください)で構成され、Azure AD のメンバー (電子メールが有効なオブジェクト) があります。 また、役割と同じ名前の役割グループを作成できます。この役割を含む場合と含めない場合があります (この混乱を避けます)。

ある意味では、これらは役割グループ モデルExchange進化しています。 ただし、Exchange Online独自の役割[グループ管理インターフェイスがあります](/exchange/permissions-exo)。 Exchange Online の一部の役割グループは、Azure AD またはセキュリティ & コンプライアンス センターからロックおよび管理されますが、同じ名前または類似の名前を持ち、Exchange Online で管理される役割グループもあります (混乱を招く)。 管理にスコープが必要Exchange Online場合を限り、ユーザー インターフェイスを使用Exchange勧めします。

カスタム ロールを作成できない。 役割は、Microsoft によって作成されたサービスによって定義され、新しいサービスが導入されるにつれて増加します。 これは概念的には、Azure [のアプリケーションで定義](/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) されたロールと似AD。 新しいサービスを有効にすると、多くの場合、新しい役割グループを作成して、アクセス権を付与または委任する必要があります (インサイダー リスク [管理など](../compliance/insider-risk-management-configure.md))。

また、これらの役割グループには直接メンバーシップが必要であり、Azure の役割グループADできません。 残念ながら、現在、これらの役割グループは、AZURE および PIM ADされていません。 Azure ADロールと同様に、API や Saviynt のようなパートナー ガバナンス製品を使用してこれらの管理を推奨する傾向があります。

セキュリティ & コンプライアンス センターの役割は Microsoft 365 にまたがり、これらの役割グループを環境のサブセット (Azure AD の管理単位と同様に) にスコープ設定することはできません。 多くのお客様は、どのようにサブ代理を行うのかについて質問します。 たとえば、「EU ユーザー専用の DLP ポリシーを作成する」とします。 現在、セキュリティ コンプライアンス センターで特定の機能に対する権限を持っている&、テナント内のこの機能の対象となるすべての機能に対する権限を持っています。 ただし、多くのポリシーには、環境のサブセットを対象とする機能があります (たとえば、「これらのラベルを[](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)これらのユーザーのみが使用できる」など)。 適切なガバナンスとコミュニケーションは、競合を避けるための重要なコンポーネントです。 一部のお客様は、セキュリティ コンプライアンス センターでサブプロジェクトに対処するための "コードとしての構成" アプローチを実装&選択します。 一部の特定のサービスでは、サブプロジェクトがサポートされています (以下を参照)。

セキュリティ & コンプライアンス センター (protection.office.com) を通じて現在管理されているコントロールは、security.microsoft.com と compliance.microsoft.com の 2 つの別個の管理ポータルに移行中です。 変更は唯一の定数です。

### <a name="service-specific"></a>サービス固有

前に述べたように、多くのお客様は、より詳細な委任モデルの実現を探しています。 一般的な例: "Division X のユーザーと場所の XYZ サービスのみを管理する" (または他のディメンション)。 これを行う機能は、各サービスによって異なりますが、サービスと機能間で一貫性が保たれたものではありません。 さらに、各サービスには、個別の一意の RBAC モデルが用意されている場合があります。 これらすべてについて話し合う代わりに (永遠に時間がかかる)、各サービスに関連するリンクを追加しています。 これは完全なリストではありません。

- **Exchange Online** - (/exchange/permissions-exo/permissions-exo)
- **SharePoint -** (/sharepoint/manage-site-collection-administrators)
- **Microsoft Teams** - (/microsoftteams/itadmin-readiness)
- **電子情報開示** - (../compliance/index.yml)
  - **アクセス許可フィルター** - (../compliance/index.yml)
  - **コンプライアンスの境界** - (../compliance/set-up-compliance-boundaries.md)
  - **Advanced eDiscovery** - (../compliance/overview-ediscovery-20.md)
- **Yammer** - (/yammer/manage-yammer-users/manage-yammer-admins)
- **複数地域** - (../enterprise/add-a-sharepoint-geo-admin.md)
- **Dynamics 365** – (/dynamics365/)

  注: このリンクはドキュメントのルートです。 管理/委任モデルには、バリエーションを持つ複数の種類のサービスがあります。

- **Power Platform** - (/power-platform/admin/admin-documentation)
  - **Power Apps** - (/power-platform/admin/wp-security)

    注: 管理者/委任モデルには、バリエーションを持つ複数の種類があります。

  - **Power Automate** - (/power-automate/environments-overview-admin)
  - **Power BI** - (/power-bi/service-admin-governance)

    注: データ プラットフォームのセキュリティと委任 (Power BIコンポーネント) は複雑な領域です。

- **MEM/Intune** - (/mem/intune/fundamentals/role-based-access-control)
- **エンドポイント用 Microsoft Defender** - (/windows/security/threat-protection/microsoft-defender-atp/user-roles)
- **Microsoft 365 Defender** - (../security/defender/m365d-permissions.md)
- **Microsoft Cloud App Security** - (/cloud-app-security/manage-admins)
- **Stream** - (/stream/assign-administrator-user-role)
- **情報バリア** - (../compliance/information-barriers.md)

### <a name="activity-logs"></a>アクティビティ ログ

Office 365監査ログ[が統合されています](../compliance/search-the-audit-log-in-security-and-compliance.md)。 これは非常に詳細 [なログですが](/office/office-365-management-api/office-365-management-activity-api-schema)、名前をあまり読み込む必要があります。 セキュリティとコンプライアンスのニーズに必要なすべてまたは必要な情報が含まれているとは言い得ない場合があります。 また、一部のお客様は高度な監査に [本当に関心があります](../compliance/advanced-audit.md)。

他の API Microsoft 365アクセスされるログの例を次に示します。

- [Azure AD](/azure/azure-monitor/platform/diagnostic-settings) (ユーザーに関連しないアクティビティOffice 365)
- [Exchangeメッセージ追跡](/powershell/module/exchange/get-messagetrace)
- 上記で説明した脅威/UEBA システム (Azure AD Identity Protection、Microsoft Cloud App Security、Microsoft Defender for Endpoint など)
- [Microsoft の情報保護](../compliance/data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

まず、セキュリティとコンプライアンス プログラムに必要なすべてのログ ソースを特定することが重要です。 また、ログごとにオンライン保持制限が異なる点にも注意してください。

管理者委任の観点から見ると、Microsoft 365アクティビティ ログには組み込みの RBAC モデルが含まれます。 ログを表示するアクセス許可がある場合は、ログ内のすべての情報を表示できます。 顧客の要件の一般的な例は、「EU ユーザーに対してのみアクティビティをクエリする」(または他のディメンション)です。 この要件を実現するには、ログを別のサービスに転送する必要があります。 Microsoft クラウドでは、Azure [Sentinel](/azure/sentinel/overview) または Log Analytics に転送 [することをお勧めします](/azure/azure-monitor/learn/quick-create-workspace)。

高レベルの図:

![セキュリティおよびコンプライアンス プログラムのログ ソースの図。](../media/solutions-architecture-center/identity-beyond-illustration-4.png)

上の図は、イベント ハブや Azure Log Analytics にログを送信する組み込Azure Storageを表しています。 一部のシステムには、このアウトオブザボックスがまだ含まれる場合があります。 ただし、これらのログを同じリポジトリに送信する他の方法があります。 たとえば[、「Azure Sentinel を使用してTeams保護する」を参照してください](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761)。

すべてのログを 1 つの保存場所に組み合わせるには、相互相関、カスタム保持時間、RBAC モデルをサポートするために必要なデータの拡張など、追加の利点があります。 このストレージ システムにデータが含まれると、適切な RBAC モデルPower BIダッシュボード (または別の種類の視覚化) を作成できます。

ログは 1 つの場所にのみ向けられる必要があります。 また、ログを Office 365または[](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)カスタム RBAC モデルMicrosoft Cloud App Securityに統合する場合[Power BI。](../admin/usage-analytics/usage-analytics.md) リポジトリごとに利点と対象ユーザーが異なります。

Microsoft 365 Defender と呼ばれるサービスには、セキュリティ、脅威、脆弱性などのための非常に豊富な組み込みの分析[システムがあります](../security/defender/microsoft-365-defender.md)。

大規模な顧客の多くは、このログ データをサードパーティのシステム (SIEM など) に転送したいと思っています。 これにはさまざまな方法がありますが、一般的な[Azure Event Hub](/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) [と](/graph/security-integration)Graph開始点です。

### <a name="azure"></a>Azure

Azure AD、Azure、SaaS の間で高い特権の役割を分離する方法がある場合(たとえば、Azure のグローバル管理者Office 365が、Azure ではない) という質問が頻繁に表示されます。  いやそうではありません。  完全な管理分離が必要な場合は、マルチテナント アーキテクチャが必要ですが、その場合は非常に複雑になります [(上記](https://aka.ms/multi-tenant-user) を参照)。 これらのサービスはすべて、同じセキュリティ/ID 境界の一部です (上記の階層モデルを参照してください)。

同じテナント内のさまざまなサービス間の関係を理解することが重要です。 Azure、Office 365、Power プラットフォーム (多くの場合はオンプレミスおよびサード パーティのクラウド サービス) にまたがるビジネス ソリューションを構築している多くのお客様と仕事をしています。 一般的な例を次に示します。

1. 一連のドキュメント/画像/etc で共同作業したい (Office 365)
2. 承認プロセスを通じて各 1 つを送信する (Power Platform)
3. すべてのコンポーネントが承認された後、これらを統合成果物 (Azure) (Azure) に組みGraph [API は](/azure/active-directory/develop/microsoft-graph-intro)、これらの親友です。  不可能ではないが、複数のテナントにまたがるソリューションを設計する方 [が非常に複雑です](/azure/active-directory/develop/single-and-multi-tenant-apps)。

Azure Role-Based アクセス制御 (RBAC) を使用すると、Azure の詳細なアクセス管理が可能になります。 RBAC を使用すると、ユーザーにジョブの実行に必要なアクセス許可を最も少なくすることで、リソースへのアクセスを管理できます。 詳細は、このドキュメントの範囲を外していますが、RBAC の詳細については、「Azure の役割ベースのアクセス制御 [(RBAC) とは」を参照してください。](/azure/role-based-access-control/overview) RBAC は重要ですが、Azure のガバナンスに関する考慮事項の一部に限定されます。 [クラウド導入フレームワークは](/azure/cloud-adoption-framework/govern/) 、詳細を学ぶ上で最適な開始点です。 私は友人の [Andres Ravinet](https://www.linkedin.com/in/andres-ravinet/)が、アプローチを決定するさまざまなコンポーネントを使用して、顧客を一歩一歩進める方法が好きです。 さまざまな要素 (実際の顧客モデルにアクセスするプロセスほど良いではない) のハイレベル ビューは次のようなものです。

![委任された管理用の Azure コンポーネントのハイレベル ビュー。](../media/solutions-architecture-center/identity-beyond-illustration-5.png)

上の図から分かっている通り、他の多くのサービスはデザインの一部として考慮する必要があります [(Azure Policies、Azure](/azure/governance/policy/overview) [Blueprints、Management](/azure/governance/blueprints/overview) [Groups](/azure/governance/management-groups/)など)。

## <a name="conclusion"></a>まとめ

短い要約として開始され、予想よりも長く終わりました。  組織の委任モデルの作成に関する詳細な説明に取り組む準備が整いました。  この会話は、お客様と非常に一般的です。 すべてのユーザーに対応するモデルは 1 つはありません。 Microsoft エンジニアリングからいくつかの計画的な改善を待ち、お客様に共通のパターンを文書化します。 その間、Microsoft アカウント チームと一緒に、最寄りの Microsoft テクノロジ センターへの訪問 [を手配できます](https://www.microsoft.com/mtc)。  そこでお会いしましょう!
