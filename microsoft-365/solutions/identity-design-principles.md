---
title: Microsoft 365 エンタープライズ リソース計画 - セキュリティ アーキテクチャ
description: Microsoft のテクニカル プリンシパル アーキテクト、Alex Shteynberg 氏による Microsoft Enterprise アーキテクチャのトップ 設計戦略について説明します。
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
ms.openlocfilehash: 00fede86da826b940026b894a4ba2a9774ae4dc2
ms.sourcegitcommit: ddfb4f3e34deb733e8625e845e4dfd1fcc066ceb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49771909"
---
# <a name="to-identity-and-beyondone-architects-viewpoint"></a>アイデンティティとそれ以降 - 1 つのアーキテクトの視点

この記事では、Microsoft のプリンシパル 技術アーキテクトである [Alex Shteynberg](https://www.linkedin.com/in/alex-shteynberg/)氏が、Microsoft 365 および他の Microsoft クラウド サービスを採用するエンタープライズ組織のトップ 設計戦略について説明します。

## <a name="about-the-author"></a>筆者について

![Alex Shteynberg の写真](../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg)

私はニューヨークの Microsoft テクノロジ センターのプリンシパル [技術アーキテクトです](https://www.microsoft.com/mtc?rtc=1)。 私は、主に大規模な顧客や複雑な要件に対応しています。 私の考えや意見は、これらのやり取りに基づいており、すべての状況に当てはめられるとは言えなす場合があります。 しかし、私の経験では、最も複雑な課題にお客様を支援できる場合は、すべてのお客様を支援できます。

私は通常、毎年 100 以上の顧客と一緒に作業します。 すべての組織に固有の特徴がある一方で、傾向と共通点を確認するのも興味深い方法です。 たとえば、1 つの傾向は多くのお客様に対する業界間の関心です。 結局のところ、銀行の支店は、喫茶店やコミュニティ センターにもなっています。

私の役割では、お客様が独自のビジネス目標に対応するために最適な技術ソリューションを提供するサポートに重点を置きます。 正式には、ID、セキュリティ、プライバシー、コンプライアンスに重点を置いて説明します。 私が行うすべての機能に触れるという事実が好きなのです。 ほとんどのプロジェクトに関わる機会を得る機会になります。 これにより、非常に忙しく、この役割を楽しみます。

私はニューヨークに住んでいて (最高です)、その文化、食料、人の多様性を楽しんでいる (トラフィックではない)。 私は旅行が可能で、私の一生の間にほとんどの世界を見る機会を希望しています。 私は現在、アフリカへの旅行を調査して、自然について学んでいます。

## <a name="guiding-principles"></a>ガイドの原則

- **多くの場合、シンプル** な方が優れた方法です。テクノロジを使用して(ほとんど) 何でも実行できますが、必ず行う必要はありません。 特にセキュリティ領域では、多くのお客様がソリューションに過剰に対応しています。 Google の [Stripe 会議のこの](https://www.youtube.com/watch?v=SOQgABDSYZE) ビデオは、この点をアンダースコアで示すのが好きです。
- **人、プロセス、テクノロジ**: [技術ではなく](https://en.wikipedia.org/wiki/Human-centered_design) 、プロセスを強化する人のための設計。 "完全な" ソリューションはありません。 さまざまなリスク要因のバランスを取る必要があります。意思決定はビジネスごとに異なります。 ユーザーが後で避ける方法を設計する顧客が多すぎます。
- **最初に 「理由」と後で「方法**」に焦点を当てる: 100 万件の質問で迷惑な 7 yr 古い子供になる。 適切な質問がない場合、正しい回答は得りません。 多くのお客様は、ビジネス上の問題を定義する代わりに、どのように動作する必要があるのかを前提にしています。 使用できるパスは常に複数です。
- **過去のベスト プラクティスの長い** 尾部 : ベスト プラクティスが明るい速度で変化することを認識します。 3 か月以上前に Azure ADを見た場合は、有効期限が切れた可能性があります。 ここに記載されている内容はすべて、公開後に変更される可能性があります。 今日の "最適" オプションは、今から 6 か月後に同じではない可能性があります。

## <a name="baseline-concepts"></a>ベースラインの概念

このセクションは省略してください。 クラウド サービスを何年も使用しているお客様も含め、多くの場合、これらのトピックに戻る必要があります。
言語は正確なツールではない。 多くの場合、同じ単語を使用して、異なる概念や異なる単語を意味し、同じ概念を意味します。 以下の図を使用して、いくつかのベースライン用語と "階層モデル" を確立します。
<br><br>

![テナント、サブスクリプション、サービス、およびデータの図](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)  

<br>

海に入る方法を学んだら、プールから始め、海の真ん中ではなくプールから始める方が良い方法です。 この図を技術的に正確に扱おうとはしていない。 これは、いくつかの基本的な概念について説明するモデルです。

図の説明

- Tenant = Azure AD のインスタンス。 これは、階層の "一番上" または図のレベル 1 です。 これは、他のすべてが発生する["境界](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-directory-independence)" と見なします (Azure AD[B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) を除く)。 すべての Microsoft エンタープライズ クラウド サービスは、これらのテナントの 1 つの一部です。 コンシューマー サービスは独立しています。 「テナント」は、365 テナントOffice Azure テナント、WVD テナントなどのドキュメントに表示されます。 多くの場合、これらのバリエーションは顧客に混乱を招く場合があります。
- 図のレベル 2 であるサービス/サブスクリプションは、1 つのテナントにのみ属します。 ほとんどの SaaS サービスは 1 対 1 で、移行なしでは移行できます。 Azure は異なります。請求 [やサブスクリプションを](https://docs.microsoft.com/azure/cost-management-billing/manage/billing-subscription-transfer) 別のテナント [に](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) 移動できます。 Azure サブスクリプションを移動する必要がある多くのお客様がいます。 これにはさまざまな影響があります。 サブスクリプションの外部に存在するオブジェクトは移動しません (たとえば、役割ベースのアクセス制御、Azure RBAC、Azure AD オブジェクト (グループ、アプリ、ポリシーなど)。 また、一部のサービス (Azure Key Vault、データ ブロックなど)。 ビジネス上の良い必要性がない場合は、サービスを移行しない。 移行に役立つスクリプトの一部は [、GitHub で共有されています](https://github.com/lwajswaj/azure-tenant-migration)。
- 特定のサービスには、通常、何らかの "サブレベル" 境界、またはレベル 3 (L3) があります。 これは、セキュリティ、ポリシー、ガバナンスなど、分離について理解するために役立ちます。 残念ながら、知っている統一された名前はありません。 L3 の名前の例には、Azure Subscription = [resource があります](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resources-portal)。Dynamics 365 CE = [インスタンス](https://docs.microsoft.com/dynamics365/admin/new-instance-management);Power BI = [ワークスペース](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces);Power Apps = [環境](https://docs.microsoft.com/power-platform/admin/environments-overview);などなど。
- レベル 4 は、実際のデータが保存されている場所です。 この 「データ平面」は複雑なトピックです。 一部のサービスは RBAC 用に Azure ADを使用し、他のサービスは使用していないサービスです。 委任に関するトピックにアクセスする場合は、少し説明します。

多くのお客様 (および Microsoft の従業員) が混乱している、または次のような疑問を持っているその他の概念があります。

- 誰でも [多くの](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) テナントをコストを [必要としません](https://azure.microsoft.com/pricing/details/active-directory/)。 その中でサービスを準備する必要はない。 数十個のデータがあります。 各テナント名は、Microsoft の世界規模のクラウド サービスで一意です (つまり、同じ名前を持つテナントは 2 つはありません)。 これらはすべて、ファイル形式TenantName.onmicrosoft.com。 テナントを自動的に作成するプロセス (非管理対象テナント)[も用意されています](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup)。 たとえば、ユーザーが他のテナントに存在しない電子メール ドメインを使用してエンタープライズ サービスに登録すると、このエラーが発生する可能性があります。
- 管理されたテナントでは、多数の [DNS ドメイン](https://docs.microsoft.com/azure/active-directory/fundamentals/add-custom-domain) をそのテナントに登録できます。 これにより、元のテナント名は変更されません。 現在、テナントの名前を変更する簡単な方法はありません (移行以外)。 最近、テナント名は技術的に重要ではありませんが、一部のテナント名は制限されている可能性があります。
- サービスの展開をまだ計画していない場合でも、組織のテナント名を予約する必要があります。 それ以外の場合、誰かがそれを取得して、それを取り戻す簡単なプロセスはありません (DNS 名と同じ問題)。 この方法は、お客様から頻繁に聞こえ過ぎます。 テナント名も議論の的です。
- DNS 名前空間を所有している場合は、これらすべての名前空間をテナントに追加する必要があります。 それ以外の場合は、この名前のアン [マネージ](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) テナントを作成し、管理の中断 [を引き起こす可能性があります](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)。
- DNS 名前空間 (contoso.com など) は、1 つのテナントにのみ属することができます。 これは、さまざまなシナリオに影響を与えます (たとえば、合併や買収時に電子メール ドメインを共有することなど)。 DNS サブ (div.contoso.com など) を別のテナントに登録する方法がありますが、これは避ける必要があります。 トップ レベルのドメイン名を登録すると、すべてのサブドメインが同じテナントに属すると見なされます。 マルチテナントのシナリオ (下記参照) では、通常、別のトップ レベル ドメイン名 (contoso.ch や ch-contoso.com) を使用することをお勧めします。
- テナントを "所有" する必要があります。 多くの場合、テナントを現在所有しているユーザーを知らないお客様が表示されます。 これは大きな赤いフラグです。 Microsoft サポートに ASAP を問い合わせください。 同様に、サービス所有者 (多くの場合、Exchange 管理者) がテナントを管理するために指定されている場合も同様です。 テナントには、今後必要なすべてのサービスが含まれる予定です。 テナントの所有者は、組織内のすべてのクラウド サービスの有効化を決定できるグループである必要があります。 もう 1 つの問題は、テナント所有者グループがすべてのサービスを管理する必要がある場合です。 これは大規模な組織では拡大縮小しない。
- サブ/スーパー テナントの概念はありません。 何らかの理由で、この日は繰り返し続ける必要があります。 これは、Azure AD [B2C](https://docs.microsoft.com/azure/active-directory-b2c/) テナントにも適用されます。 「B2C 環境が XYZ テナントにある」、または「Azure テナントを Office 365 テナントに移行する方法」という何度も聞こえます。
- このドキュメントでは、ほとんどのお客様が使用しているのが商用の世界規模のクラウドに主に焦点を当てています。 主権を持つクラウドについて [知っているのは役に立つ場合があります](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud)。 主権を持つクラウドは、この議論の対象範囲を超えるものに関して、追加の意味を持っています。

## <a name="baseline-identity-topics"></a>ベースライン ID に関するトピック

Microsoft の ID プラットフォームである Azure Active Directory (Azure active Directory) に関する多くのドキュメントAD。 始め過ごしたばかりのユーザーには、多くの場合、圧倒感を感じる場合があります。 学習した後でも、絶え間ない技術革新と変化に付き合うのは困難な場合があります。 お客様とのやり取りでは、多くの場合、ビジネス目標と、これらに対処するための 「良い、最高」のアプローチ (およびこれらのトピックの人間的な「メモ」) の間で「翻訳者」として機能しています。 完全な答えはまれで、"正しい" 決定はさまざまなリスク要因のバランスです。 以下は、お客様と話し合う一般的な質問と混乱の分野の一部です。

### <a name="provisioning"></a>プロビジョニング

Azure ADでは、ID の世界にガバナンスが存在しないという問題は解決しません。 [ID ガバナンスは](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) 、クラウド上の決定に依存しない重要な要素である必要があります。 ガバナンス要件は時間の間に変化します。これは、それがツールではなくプログラムである理由です。

[Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect) と [Microsoft Identity Manager](https://docs.microsoft.com/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) の違い、または他の何か (サード パーティまたはカスタム)? 現在および将来、多くの問題を自分を保存し、Azure AD Connect を使用します。 このツールには、お客様の多大な構成と継続的な技術革新に対応するためのあらゆる種類のスマートがあります。

より複雑なアーキテクチャに向かう可能性のあるエッジ ケースは次の場合があります。

- これらの間にネットワークAD接続のない複数のフォレストがあります。 クラウド プロビジョニングという新しい [オプションがあります](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning)。
- Active Directory を持たなかったり、インストールしたりしない。 Azure AD CONNECT は LDAP から [同期するように構成](https://docs.microsoft.com/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) できます (パートナーが必要な場合があります)。
- 同じオブジェクトを複数のテナントにプロビジョニングする必要があります。 これは技術的にはサポートされていませんが、"同じ" の定義に依存します。

既定の同期ルール (フィルター[オブジェクト、変更属性](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering)[、](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)代替ログイン[ID](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-userprincipalname)など) をカスタマイズする必要がありますか。 これは避ける必要があります。 ID プラットフォームは、ID プラットフォームを使用するサービスと同じだけの価値があります。 あらゆる種類の簡単な構成を行えますが、この質問に答えるには、アプリケーションへの影響を確認する必要があります。 メールが有効なオブジェクトをフィルター処理すると、オンライン サービスの GAL は不完全になります。アプリケーションが特定の属性に依存している場合、これらをフィルター処理すると予期しない影響があります。などなど。 ID チームの決定ではありません。

XYZ SaaS は Just-in-Time (JIT) プロビジョニングをサポートしています。同期を要求する理由は何ですか? 上記を参照してください。 多くのアプリケーションでは、機能に "プロファイル" 情報が必要です。 メールが有効なすべてのオブジェクトが使用できない場合は、GAL を使用できません。 Azure AD[](https://docs.microsoft.com/azure/active-directory/app-provisioning/user-provisioning)と統合されたアプリケーションでのユーザー プロビジョニングにもAD。

### <a name="authentication"></a>認証

[パスワード ハッシュ同期](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) (PHS) [とパススルー認証](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (PTA) [対フェデレーション](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility)。

通常、フェデレーションに関 [する議論](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) は大きな議論の的です。 通常は、より単純な方が優れた方法なので、それ以上の理由がない限り PHS を使用します。 同じテナント内の DNS ドメインごとに異なる認証方法を構成できます。 

一部のお客様は、主に次の場合にフェデレーション + PHS を有効にしています。

- フェデレーション サービス [が使用できない](https://docs.microsoft.com/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) 場合に (障害復旧用に) フォール バックするオプション。
- その他の機能 (例: [Azure AD DS)](https://docs.microsoft.com/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)とセキュリティ サービス (例: 漏洩 [した資格情報](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials))
- フェデレーション認証を理解しない Azure のサービス [(Azure ファイル](https://docs.microsoft.com/azure/storage/files/storage-files-active-directory-overview)など) のサポート。

多くの場合、クライアント認証フローを通して、いくつかの誤解を明確にしています。 結果は次の図のようになりますが、この図は、そこに表示される対話型プロセスほど良くなっています。

![ホワイトボード会話の例](../media/solutions-architecture-center/identity-beyond-whiteboard-example.png)

この種類のホワイトボード図面は、認証要求のフロー内でセキュリティ ポリシーが適用される場所を示しています。 この例では、Active Directory フェデレーション サービス (AD FS) を通じて適用されたポリシーが最初のサービス要求に適用されますが、それ以降のサービス要求には適用されません。 これは、セキュリティコントロールを可能な限りクラウドに移動する少なくとも 1 つの理由です。

シングル サインオン (SSO) の忘[](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)れは、思い出す限り続けました。 一部のお客様は、"適切な" フェデレーション (STS) プロバイダーを選択することでこれを実現できると考えています。 Azure AD SSO 機能を有効に [するのに](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-sso-deployment) 大きく役立ちますが、STS は魅力的な機能はありません。 重要なアプリケーションでまだ使用されている "レガシ" 認証方法が多すぎます。 パートナー ソリューションで Azure AD [を拡張すると、これらのシナリオ](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) の多くを解決できます。 SSO は戦略と行い方です。 アプリケーションの標準に進 [む必要があります](https://docs.microsoft.com/azure/active-directory/develop/v2-app-types)。 このトピックに関連する、パスワードレス[](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)認証への取り込みも、魔法の答えはありません。

[多要素認証](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) は現在不可欠です ([詳しくは、](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) ここをご覧ください)。 ユーザーの行動 [分析に追加](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) すると、最も一般的なサイバー攻撃を防止するソリューションが用意されています。 コンシューマー サービスでさえ、MFA を要求する動きをしています。 しかし、私はまだ、最新の認証アプローチに移行したくない多くのお客様 [と](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview) 会っています。 最も聞こえる引数は、ユーザーやレガシ アプリケーションに影響を与えるという言葉です。 お客様の動きが良い場合があります -Exchange Online が変更を [発表しました](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282)。 多くの Azure AD [レポートを利用](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) して、この移行のお客様を支援しています。

### <a name="authorization"></a>Authorization

Wikipedia [ごとに](https://en.wikipedia.org/wiki/Authorization)、"承認する" のはアクセス ポリシーを定義する方法です。 多くのユーザーは、オブジェクト (ファイル、サービスなど) へのアクセス制御を定義する機能と見なされます。 サイバー脅威の現在の世界では、この概念は、さまざまな脅威ベクトルに対応し、これらに対応してアクセス制御をすばやく調整できる動的ポリシーに急速に進化しています。 たとえば、異常な場所から銀行口座にアクセスすると、追加の確認手順が表示されます。 この問題に取り組むには、ポリシー自体だけでなく、脅威検出とシグナル相関の方法論のエコシステムも考慮する必要があります。

Azure ADのポリシー エンジンは、条件付きアクセス ポリシー [を使用して実装されます](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。 このシステムは、動的な決定を行う他のさまざまな脅威検出システムからの情報に依存しています。 単純なビューは、次の図のようになります。

![Azure AD のポリシー エンジン](../media/solutions-architecture-center/identity-and-beyond-illustration-3.png)

これらすべてのシグナルを組み合わせると、次のような動的ポリシーが可能です。

- デバイスで脅威が検出された場合、データへのアクセスは、ダウンロード機能なしで Web にのみ削減されます。
- 異常に多くのデータをダウンロードしている場合、ダウンロードするデータは暗号化され、制限されます。
- 非管理対象デバイスからサービスにアクセスすると、機密性の高いデータからブロックされますが、別の場所にコピーすることなく、制限されていないデータにアクセスできます。

この拡張された承認定義に同意する場合は、追加のソリューションを実装する必要があります。 どのソリューションを実装する場合は、ポリシーを動的に設定し、どの脅威に優先順位を付けるかによって異なる場合があります。 このようなシステムの例を次に示します。

- [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/) 
- [Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/)
- [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) (MCAS)
- [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/mem/intune/)
- [Microsoft Information Protection](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) (MIP)
- [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/)

もちろん、Azure AD に加えて、さまざまなサービスやアプリケーションには独自の認証モデルがあります。 これらの一部については、後の「委任」セクションで説明します。

### <a name="audit"></a>監査

Azure ADには、詳細な [監査およびレポート機能](https://docs.microsoft.com/azure/active-directory/reports-monitoring/) があります。 ただし、これは通常、セキュリティ上の決定に必要な唯一の情報源ではありません。 詳細については、「委任」セクションを参照してください。

## <a name="theres-no-exchange"></a>Exchange がない

焦らないで下さい！ これは、Exchange が廃止される (または SharePoint など) ことを意味しているという意味ではありません。 これは、依然としてコア サービスです。 つまり、今のところ、テクノロジ プロバイダーは、ユーザー エクスペリエンス (UX) を複数のサービスのコンポーネントに移行しています。 Microsoft 365 では、単純な例[として"モダン](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)添付" があります。この場合、電子メールの添付ファイルは SharePoint Online または OneDrive for Business に保存されます。

![電子メールへのファイルの添付](../media/solutions-architecture-center/modern-attachments.png)

Outlook クライアントを見て、Exchange ではなく、このエクスペリエンスの一部として "接続" されている多くのサービスを確認できます。 これには、Azure AD、Microsoft Search、アプリ、プロファイル、コンプライアンス、および Office 365 グループが含まれます。 

![吹き出しを含む Outlook インターフェイス](../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png)

今後の [機能のプレビューについては、Microsoft Fluid Framework](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) についてお読みください。 プレビューで、Outlook で Teams の会話を直接読んで返信できます。 実際 [、Teams クライアントは、この](https://products.office.com/microsoft-teams/download-app) 戦略の最も目立った例の 1 つです。 

全体として、365 と Microsoft クラウドの他のサービスの間に明確Office線を引くのは困難になっていました。 私は、1 つのコンポーネントを使用している場合でも、すべての機能で技術革新の恩恵を受け、お客様にとって大きなメリットと見なしています。 非常にかっこよく、多くのお客様に大きな影響を与えています。

現在、多くのお客様の IT グループは"製品" を中心に構成されています。 特定の製品ごとに専門家が必要な場合は、オンプレミスの世界に対して論理的です。 しかし、これらのサービスがクラウドに移行するに従って、Active Directory データベースや Exchange データベースを再びデバッグする必要がなんかなんかないというのが、私は本当にうれしく思います。 オートメーション (クラウドの種類) は、特定の繰り返し手動ジョブを削除します (工場に何が起こったかを確認します)。 ただし、これらは、サービス間の相互作用、影響、ビジネス ニーズなどについて理解するために、より複雑な要件に置き換えられる。 学習する必要がある場合 [は](https://docs.microsoft.com/learn/)、クラウドの変換によって大きな機会を得る機会があります。 テクノロジに飛び込む前に、IT スキルとチーム構造の変化を管理する方法について、お客様によくお話しします。

すべての SharePoint ファンユーザーと開発者に対して、「SharePoint Online で XYZ を実行する方法」の質問は停止してください。 ワークフロー [に Power Automate](https://docs.microsoft.com/power-automate/) (または Flow) を使用すると、より強力なプラットフォームになります。 [Azure Bot Framework を使用](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0)して、500 K アイテム リストの優れた UX を作成します。 CSOM [の代](https://developer.microsoft.com/graph/) わりに Microsoft Graph の使用を開始します。 [Microsoft Teams には](https://docs.microsoft.com/MicrosoftTeams/Teams-overview) SharePoint だけでなく、より多くの世界が含まれています。 リストできる他の多くの例があります。 そこには膨大な数の大きな問題が存在します。 ドアを開き [、探索を開始します](https://docs.microsoft.com)。

もう 1 つの一般的な影響は、コンプライアンスの領域です。 このクロスサービス アプローチは、多くのコンプライアンス ポリシーを完全に混同しているようです。 「すべての電子メール通信を電子情報開示システムにジャーナル処理する必要がある」と記載されている組織を見続ける。 メールが単なる電子メールではなく、他のサービスへのウィンドウである場合、これは本当に何を意味しますか? Office 365 にはコンプライアンスのための包括的な[](https://docs.microsoft.com/microsoft-365/compliance/)アプローチがありますが、多くの場合、人やプロセスの変更はテクノロジよりもはるかに困難です。

他にも多くの人とプロセスへの影響があります。 私の意見では、これは重要で、議論の少ない領域です。 おそらく、別の記事で詳しい記事を参照してください。

## <a name="tenant-structure-options"></a>テナント構造のオプション

### <a name="single-tenant-vs-multi-tenant"></a>シングル テナントとマルチテナント

一般に、ほとんどのお客様は、実稼働テナントを 1 つしか持たできません。 複数のテナントが難しい [(Bing](https://www.bing.com/search?q=office%20365%20multiple%20tenants)検索を提供する) か、このホワイト ペーパーを読むには、多くの [理由があります](https://aka.ms/multi-tenant-user)。 同時に、私が一緒に作業している多くの企業のお客様は、IT 学習、テスト、実験用に別の (小規模) テナントを持っています。 Azure Azure Azure を使用すると、テナント間の Azure アクセス [が容易になります](https://azure.microsoft.com/services/azure-lighthouse/)。 Office 365 および他の多くの SaaS サービスでは、テナント間のシナリオに制限があります。 Azure および B2B のシナリオでは [AD検討する必要](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) があります。

多くのお客様は、合併と合併 (M&A) の後に複数の実稼働テナントに対応し、統合を望む場合があります。 今日では、これは単純ではなく、Microsoft Consulting Services (MCS) またはパートナーとサード パーティ製ソフトウェアが必要です。 マルチテナントのお客様とのさまざまなシナリオに対応するエンジニアリング作業が今後進行中です。

一部の顧客は、複数のテナントと一緒に行く選択をします。 これは非常に慎重な決定であり、ほとんどの場合、ビジネス上の理由が大きな影響を受けます。 以下に例を示します。

- 異なるエンティティ間の簡単なコラボレーションが必要ではなく、強力な管理や他の分離のニーズがある、持ち込みタイプの会社の構造。
- 取得後、2 つのエンティティを分離するビジネス上の決定が行います。
- お客様の実稼働環境を変更しない、お客様の環境のシミュレーション。 
- お客様向けソフトウェアの開発。

このようなマルチテナント のシナリオでは、多くの場合、テナント間で構成を同じにしたり、構成の変更や違いについて報告したりしたいと考える場合があります。 これは、多くの場合、手動による変更からコードとしての構成への移行を意味します。 Microsoft のサポートは、このパブリック IP に基づいて、これらの種類の要件に関するワークショップを提供します [https://Microsoft365dsc.com](https://Microsoft365dsc.com) 。

### <a name="multi-geo"></a>Multi-Geo

複数 [地域の場合](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo) と複数地域ではない場合は、それが問題です。 Office 365 Multi-Geo を使用すると、データ常駐の要件を満たすために選択した地理的位置に保存されたデータをプロビジョニングして [保存できます](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations) 。 この機能には多くの誤解があります。 以下の点にご注意ください:

- パフォーマンス上のメリットを提供するのではありません。 ネットワーク設計が正しくなされていないと、 [パフォーマンスが](https://aka.ms/office365networking) 低下する可能性があります。 Microsoft ネットワークに "近い" デバイスを取得します。必ずしもデータに近いとは限りません。
- GDPR コンプライアンスの [ソリューションではありません](https://www.microsoft.com/trust-center/privacy/gdpr-overview)。 GDPR では、データ主権や保存場所には焦点を当ててない。 その他のコンプライアンス フレームワークがあります。
- 管理の委任 (下記参照) や情報障壁 [は解決しません](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)。
- マルチテナントと同じではなく、追加のユーザー プロビジョニング [ワークフローが](https:/docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) 必要です。
- テナント (Azure [AD)](https://docs.microsoft.com/microsoft-365/enterprise/moving-data-to-new-datacenter-geos) が別の地域に移動されるのではありません。 

## <a name="delegation-of-administration"></a>管理の委任

ほとんどの大規模な組織では、職務と役割ベースのアクセス制御 (RBAC) の分離が必要です。 私は前もって申し訳ない。 これは、一部のお客様が望むほど単純ではありません。 お客様、法律、コンプライアンス、その他の要件は異なっています。また、世界中で競合する場合があります。 シンプルさと柔軟性は、多くの場合、互いに反対側に位置します。 私を間違えめないで、これでより良い仕事をすることができます。 時間の長い間、大幅な改善が行されています (今後も大幅に改善されます)。 379230 ドキュメントを読むことなく、お客様のビジネス要件に適合するモデルを確認するには、お近くの [Microsoft](https://www.microsoft.com/mtc) テクノロジ センターをご覧ください。 ここでは、この方法の理由ではなく、何を考えるべきかについて焦点を当てるとします。 以下は、計画する 5 つの異なる領域と、よく発生した質問の一部です。

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Azure AD Microsoft 365 管理センター

組み込みの役割の長いリスト [が増え続けています](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 各役割は、特定のアクションを実行するためにグループ化された役割のアクセス許可の一覧で構成されます。 これらのアクセス許可は、各ロール内の [説明] タブで確認できます。 または、Microsoft 365 管理センターで、より人間が読み取り可能なバージョンを表示できます。 組み込みのロールの定義は変更できません。 一般に、これらを 3 つのカテゴリにグループ化します。

- **グローバル管理者**: この "すべての強力な [](https://docs.microsoft.com/microsoft-365/enterprise/protect-your-global-administrator-accounts)" 役割は、他のシステムと同様に高度に保護する必要があります。 一般的な推奨事項には、永続的な割り当てはなし、Azure AD Privileged Identity Management (PIM) の使用が含まれます。強力な認証などなど。 興味深いことに、この役割では、既定ですべてのアクセス権が与えらという意味で、この役割は提供されません。 通常、コンプライアンス アクセスと Azure アクセスについては、後で説明します。 ただし、このロールは常に、テナント内の他のサービスへのアクセスを割り当てできます。 
- **特定のサービス管理者**: 一部のサービス (Exchange、SharePoint、Power BI など) は、Azure AD からの高レベルの管理ロールを使用します。 これはすべてのサービスで一貫しているのではないので、後で説明するサービス固有の役割もあります。
- **機能**: 特定の操作 (ゲスト招待者など) に焦点を当てた役割の長い (増大し続ける) リストがあります。 定期的に、これらの多くが顧客のニーズに基づいて追加されます。

すべてを委任できません (ギャップは減少しています)。つまり、グローバル管理者ロールを使用する必要がある場合があります。 コードとしての構成と自動化は、このロールのユーザー メンバーシップではなく考慮する必要があります。

**注**: Microsoft 365 管理センターの方がユーザー フレンドリーなインターフェイスを持っていますが、Azure 管理エクスペリエンスと比較して機能のサブセットADがあります。 どちらのポータルも同じ Azure ADロールを使用します。そのため、変更は同じ場所で行っています。 ヒント: Azure 低優先メール機能を使用せずに ID 管理に重点を置く管理 UI が必要な場合は、使用します [https://aad.portal.azure.com](https://aad.portal.azure.com) 。 

名前には何がありますか? ロールの名前に基づいて想定を行う必要があります。 言語は、非常に正確なツールではありません。 目標は、必要な役割を確認する前に委任する必要がある操作を定義する必要があります。 "Security Reader" ロールにユーザーを追加しても、すべてのユーザーにセキュリティ設定が表示されるというのではありません。

カスタム ロールを作成 [する機能は](https://docs.microsoft.com/azure/active-directory/users-groups-roles/roles-custom-overview) よくある質問です。 これは、現在の Azure AD制限されますが (下記参照)、時間がたつにつれて機能が拡張されます。 これらは Azure AD の関数に適用できると考えていますが、階層モデルを "ダウン" する可能性があります (上で説明しました)。 "カスタム" を扱う場合は常に、"simple の方が良い" というプリンシパルに戻る傾向があります。

もう 1 つの一般的な問題は、ロールをディレクトリのサブセットにスコープ設定する機能です。 1 つの例は、「EU のユーザー向けヘルプデスク管理者」のようなものです。 [管理単位](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-administrative-units) (AU) は、この問題に対処することを目的とします。 上記と同様に、これらは Azure ADの関数に適用できると考え、"ダウン" に及びない可能性があります。 もちろん、特定のロールはスコープに意味がありません (グローバル管理者、サービス管理者など)。

現在、これらのすべてのロールには直接メンバーシップ (または Azure または PIM を使用 [する場合は動的割り当AD必要です](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/)。 つまり、お客様は Azure AD でこれらを直接管理する必要があります。セキュリティ グループ メンバーシップに基づいて管理することはできません。 管理者特権で実行する必要があるスクリプトを管理するスクリプトを作成する方法は、私には大きな問題ではありません。 一般に、API を ServiceNow のようなプロセス システムと統合するか、Saviynt のようなパートナー ガバナンス ツールを使用することをお勧めします。 時間の中でこの問題に対処するエンジニアリング作業が行っています。

Azure AD [PIM について](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/) 何度か言及しました。 オンプレミスコントロールには、対応する Microsoft Identity Manager (MIM) [Privileged Access Management](https://docs.microsoft.com/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) (PAM) ソリューションがあります。 Privileged [Access Workstation](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAW) と Azure AD Identity Governance も [参照してください](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)。 また、さまざまなサード パーティ製ツールもあります。このツールを使用すると、Just-In-Time、Just-Enough、および動的なロール昇格を有効にできます。 これは通常、環境をセキュリティ保護するためのより大きな議論の一部です。 

シナリオによっては、外部ユーザーをロールに追加する必要があります (上記のマルチテナント セクションを参照してください)。 これは問題ありません。 [Azure AD B2B は](https://docs.microsoft.com/azure/active-directory/b2b/) 、おそらく別の記事で、お客様を説明するもう 1 つの大きな楽しいトピックです。

### <a name="security-and-compliance-center-scc"></a>セキュリティ/コンプライアンス センター (SCC)

[Office 365 Security & コンプライアンス](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) センターのアクセス許可は、"役割グループ" のコレクションであり、Azure の役割とは異ADされます。 これらの役割グループの中には、Azure AD の役割と同じ名前 (セキュリティ閲覧者など) が付き、メンバーシップが異なっている場合がある場合などです。 Azure の役割を使用ADです。 各役割グループは、1 つ以上の "役割" (同じ単語を再利用する場合の意味を参照) で構成され、Azure AD のメンバー (電子メールが有効なオブジェクト) があります。 また、役割と同じ名前の役割グループを作成できます。役割には、その役割が含まれている場合と含めない場合があります (この混乱を避ける)。

ある意味で、これらは Exchange 役割グループ モデルの進化です。 ただし、Exchange Online には独自の [役割グループ管理インターフェイス](https://docs.microsoft.com/exchange/permissions-exo) があります。 Exchange Online の一部の役割グループは、Azure AD またはセキュリティ & コンプライアンス センターからロックおよび管理されますが、同じまたは類似した名前を持ち、Exchange Online で管理されている場合もあります (混乱が生じる可能性があります)。 Exchange 管理のスコープが必要ない限り、Exchange Online ユーザー インターフェイスの使用は避けることをお勧めします。

カスタム ロールを作成できない。 ロールは、Microsoft によって作成されたサービスによって定義され、新しいサービスが導入されるにつれて拡大します。 これは、概念的には Azure [AD](https://docs.microsoft.com/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) のアプリケーションで定義されたロールに似ています。 新しいサービスを有効にすると、多くの場合、これらのサービスへのアクセスを許可または委任するために、新しい役割グループを作成する必要があります (インサイダー リスク [管理など](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure?view=o365-worldwide#step-1-required-enable-permissions-for-insider-risk-management))。

これらの役割グループは直接メンバーシップも必要であり、Azure グループとグループADできません。 残念ながら、現在、これらの役割グループは Azure および PIM ADされていません。 Azure のAD同様に、API や Saviynt のようなパートナー ガバナンス製品を通じてこれらの管理を推奨する傾向があります。

セキュリティ & コンプライアンス センターの役割は Microsoft 365 にまたがるので、これらの役割グループのスコープを環境のサブセットにすることはできません (Azure AD の管理単位を使用する場合など)。 多くのお客様は、どのように代理を行うのかについて問い合っています。 たとえば、「EU ユーザー専用の DLP ポリシーを作成する」などです。 現在、セキュリティ & コンプライアンス センターの特定の機能に対する権限を持っている場合は、テナント内のこの機能の対象となるすべての機能に対する権限を持っています。 ただし、多くのポリシーには、環境のサブセットを対象とする機能があります (たとえば、"これらのラベル[](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy)をこれらのユーザーのみが使用できる" など)。 適切なガバナンスとコミュニケーションは、競合を避けるための重要なコンポーネントです。 一部のお客様は、セキュリティ/コンプライアンス センターで"コードとしての構成" アプローチを実装して、サブ&します。 一部の特定のサービスは、サブ提供をサポートしています (下記を参照)。

セキュリティ & コンプライアンス センター (protection.office.com) を通じて現在管理されているコントロールは、security.microsoft.com と compliance.microsoft.com の 2 つの別の管理ポータルに移行中です。 変更は唯一の定数です。

### <a name="service-specific"></a>サービス固有

前に説明したように、多くのお客様は、より詳細な委任モデルを実現する必要があります。 一般的な例: "Division X のユーザーと場所に対してだけ XYZ サービスを管理する" (または他の次元)。 これを行う機能は各サービスに依存し、サービスと機能の間で一貫性が保たれたものではありません。 また、各サービスには、個別の固有の RBAC モデルが用意されている場合があります。 これらのすべてについて話し合う代わりに (それはいつまでも必要になります)、各サービスに関連するリンクを追加します。 これは完全なリストではありません。しかし、開始します。

- **Exchange Online** - [https://docs.microsoft.com/exchange/permissions-exo/permissions-exo](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- **SharePoint Online** - [https://docs.microsoft.com/sharepoint/manage-site-collection-administrators](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators) 
- **Microsoft Teams**  - [https://docs.microsoft.com/microsoftteams/itadmin-readiness](https://docs.microsoft.com/microsoftteams/itadmin-readiness )
- **電子情報開示** - [https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions](https://docs.microsoft.com/microsoft-365/compliance/) 
  + **アクセス許可フィルター**  - [https://docs.microsoft.com/microsoft-365/compliance/permissions-filtering-for-content-search](https://docs.microsoft.com/microsoft-365/compliance/)
  + **コンプライアンスの境界**  - [https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries )
  + **Advanced eDiscovery**  - [https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 )
- **Yammer** - [https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins) 
- **複数地域** - [https://docs.microsoft.com/microsoft-365/enterprise/add-a-sharepoint-geo-admin](https://docs.microsoft.com/microsoft-365/enterprise/add-a-sharepoint-geo-admin) 
- **Dynamics 365** – [https://docs.microsoft.com/dynamics365/](https://docs.microsoft.com/dynamics365/) <br>
  注: このリンクはドキュメントのルートにリンクされています。 管理/委任モデルには、バリエーションを持つ複数の種類のサービスがあります。
- **Power Platform**  - [https://docs.microsoft.com/power-platform/admin/admin-documentation](https://docs.microsoft.com/power-platform/admin/admin-documentation )
  + **Power Apps**  - [https://docs.microsoft.com/power-platform/admin/wp-security](https://docs.microsoft.com/power-platform/admin/wp-security ) <br>
    注: 管理者/委任モデルには、バリエーションを持つ複数の種類があります。
  + **Power Automate**  - [https://docs.microsoft.com/power-automate/environments-overview-admin](https://docs.microsoft.com/power-automate/environments-overview-admin )
  + **Power BI**  - [https://docs.microsoft.com/power-bi/service-admin-governance](https://docs.microsoft.com/power-bi/service-admin-governance ) <br>
注: データ プラットフォームのセキュリティと委任 (Power BI がコンポーネント) は複雑な領域です。
- **MEM/Intune**  - [https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control )
- **Microsoft Defender for Endpoint**  - [https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles )
- **Microsoft 365 Defender** - [https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions)
- **Microsoft Cloud App Security** - [https://docs.microsoft.com/cloud-app-security/manage-admins](https://docs.microsoft.com/cloud-app-security/manage-admins)
- **Stream**  - [https://docs.microsoft.com/stream/assign-administrator-user-role](https://docs.microsoft.com/stream/assign-administrator-user-role )
- **情報バリア**  - [https://docs.microsoft.com/microsoft-365/compliance/information-barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers )

残りの部分では、Docs の検索は最近は非常に良い機能でした [https://docs.microsoft.com/](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) 。 

### <a name="activity-logs"></a>アクティビティ ログ

Office 365 には、 [統合監査ログがあります](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。 非常に詳細な [ログですが](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)、名前をあまり読み込みすぎずにしてください。 セキュリティとコンプライアンスのニーズに必要なすべてが含まれているとは異なる場合があります。 また、一部のお客様は高度な監査に [関心を持っています](https://docs.microsoft.com/microsoft-365/compliance/advanced-audit)。

他の API を介してアクセスされる Microsoft 365 ログの例を次に示します。

- [Azure AD](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-settings) (Office 365 に関連しないアクティビティ)
- [Exchange メッセージ追跡](https://docs.microsoft.com/powershell/module/exchange/get-messagetrace)
- 上記の脅威/UEBA システム (たとえば、Azure AD Identity Protection、Microsoft Cloud App Security、Microsoft Defender for Endpoint など)
- [Microsoft 情報保護](https://docs.microsoft.com/microsoft-365/compliance/data-classification-activity-explorer?view=o365-worldwide)
- [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

まず、セキュリティとコンプライアンス プログラムに必要なすべてのログ ソースを特定することが重要です。 また、ログごとに異なるオンライン保持制限があります。 

管理者委任の観点から見ると、ほとんどの Microsoft 365 アクティビティ ログには RBAC モデルが組み込みではありません。 ログを表示するアクセス許可がある場合は、そのログ内のすべての情報を表示できます。 顧客要件の一般的な例として、"EU ユーザーのアクティビティのみをクエリできる" (または他の次元) があります。 この要件を満たすには、ログを別のサービスに転送する必要があります。 Microsoft クラウドでは [、Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview) または [Log Analytics](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)に転送することをお勧めします。 

高レベルの図:

![セキュリティおよびコンプライアンス プログラムのログ ソースの図](../media/solutions-architecture-center/identity-beyond-illustration-4.png)  

上の図は、イベント ハブや Azure Storage や Azure Log Analytics にログを送信する組み込みの機能を表しています。 すべてのシステムにこの機能が含まれるのは、まだありません。 ただし、これらのログを同じリポジトリに送信する別の方法があります。 たとえば [、「Azure Sentinel で Teams を保護する」を参照してください](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761)。

すべてのログを 1 つの保存場所に結合すると、相互関係、カスタム保持時間、RBAC モデルをサポートするために必要なデータの拡張など、追加の利点が含まれます。 このストレージ システムにデータが入った後、適切な RBAC モデルを使用して Power BI ダッシュボード (または別の種類の視覚化) を作成できます。

ログは 1 つの場所にのみ表示する必要があります。 また、Power BI で [Office 365 ログ](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) を Microsoft Cloud App Security またはカスタム RBAC モデルと統合する方 [が有益な場合があります](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics?view=o365-worldwide)。 リポジトリによって利点と対象ユーザーが異なります。

[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)と呼ばれるサービスには、セキュリティ、脅威、脆弱性などのための非常に豊富な組み込みの分析システムがあります。

多くの大規模な顧客は、このログ データをサード パーティ製システム (SIEM など) に転送したいと思っています。 これにはさまざまな方法がありますが、一般的な [Azure Event Hub](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) と [Graph](https://docs.microsoft.com/graph/security-integration) は良い開始点です。

### <a name="azure"></a>Azure

Azure AD、Azure、SaaS (例: Office 365 のグローバル管理者、Azure ではなくグローバル管理者) の間で高い特権ロールを分離する方法がある場合は、よく尋ねらます。  いやそうではありません。  管理の完全な分離が必要な場合はマルチテナント アーキテクチャが必要ですが、複雑さを大きくします [(上記](https://aka.ms/multi-tenant-user) を参照)。 これらすべてのサービスは、同じセキュリティ/ID 境界の一部です (上記の階層モデルを参照してください)。  

同じテナント内のさまざまなサービス間の関係を理解することが重要です。 Azure、Office 365、Power Platform (多くの場合はオンプレミスおよびサード パーティのクラウド サービス) にまたがるビジネス ソリューションを構築している多くのお客様と一緒に作業しています。 一般的な例を次に示します。

1. 一連のドキュメントや画像などに関して共同作業を行いたい (Office 365)
2. 承認プロセスを通じて各ユーザーを送信する (Power Platform)
3.  すべてのコンポーネントが承認された後、これらを統合された成果物 (Azure) の Microsoft Graph [API](https://docs.microsoft.com/azure/active-directory/develop/microsoft-graph-intro) に組み立てることは、これらのコンポーネントに最適なフレンドです。  不可能ではないが、複数のテナントにまたがるソリューションを設計する方 [が非常に複雑です](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)。

Azure Role-Based アクセス制御 (RBAC) を使用すると、Azure の詳細なアクセス管理が可能になります。 RBAC を使用すると、ユーザーにジョブの実行に必要なアクセス許可を最も少なくすることで、リソースへのアクセスを管理できます。 詳細についてはこのドキュメントでは説明できませんが、RBAC の詳細については、「Azure の役割ベースのアクセス制御 (RBAC) とは何か」を [参照してください。](https://docs.microsoft.com/azure/role-based-access-control/overview) RBAC は重要ですが、Azure のガバナンスに関する考慮事項の一部に限定されます。 [クラウド導入フレームワークは](https://docs.microsoft.com/azure/cloud-adoption-framework/govern/) 、詳細を確認する最適な開始点です。 友人の Andres 数inet は、さまざまなコンポーネントを使用してアプローチを決定する方法を、お客様をステップ バイ ステップで説明する方法が好きです。 さまざまな要素の高レベルなビュー (実際の顧客モデルにアクセスするプロセスほど良くない) は、次のようなものです。

![委任管理用の Azure コンポーネントの高レベルビュー](../media/solutions-architecture-center/identity-beyond-illustration-5.png)

上の図に示したように、他の多くのサービスは設計の一部として考慮する必要があります (例: [Azure ポリシー](https://docs.microsoft.com/azure/governance/policy/overview) [、Azure Blueprints、](https://docs.microsoft.com/azure/governance/blueprints/overview)[管理](https://docs.microsoft.com/azure/governance/management-groups/)グループなど)。

## <a name="conclusion"></a>まとめ

短い要約として開始され、予想より長く終了しました。  組織の委任モデルの作成について詳しい情報を得る準備が整いました。  この会話は、お客様に対して非常に一般的です。 すべてのユーザーに対応するモデルは 1 つではありません。 お客様全体に共通のパターンを文書化する前に、Microsoft エンジニアリングからいくつかの計画的な改善を待っています。 In the meantime, you can work with your Microsoft account team to arrange a visit to the nearest [Microsoft Technology Center](https://www.microsoft.com/mtc).  そこでお会いしましょう。
