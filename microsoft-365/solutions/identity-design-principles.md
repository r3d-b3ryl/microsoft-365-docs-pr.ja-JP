---
title: 'Id とそれ以外の場合: 1 つの設計者の視点'
description: 説明
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
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: c830e7f7b0366623520d7ba4e5a47a51e73f09ad
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160380"
---
# <a name="to-identity-and-beyond--one-architects-viewpoint"></a>Id とそれ以外の場合: 1 つの設計者の視点

この記事では、 [Alex Shteynberg](https://www.linkedin.com/in/alex-shteynberg/)、microsoft のプリンシパル技術アーキテクトが、microsoft 365 およびその他の microsoft クラウドサービスを採用しているエンタープライズ組織のための主要な設計戦略について説明します。

## <a name="about-the-author"></a>筆者について

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg" alt-text="Alex Shteynberg photo":::

私は、ニューヨークの[Microsoft テクノロジセンター](https://www.microsoft.com/mtc?rtc=1)にある主要な技術アーキテクトです。 多くのお客様や複雑な要件に対応しています。 自分の視点と意見はこれらの相互作用に基づいており、すべての状況に適用されるとは限りません。 しかし、自分の経験で、お客様が最も複雑な課題にお役立ていただける場合は、すべてのお客様を支援できます。 

通常は、毎年100人以上のお客様と協力します。 すべての組織に固有の特徴がありますが、傾向と共通点を表示することは興味深いものです。 たとえば、1つの傾向として、多くのお客様にとって業界間の関心があります。 また、銀行支店は、コーヒーショップやコミュニティセンターにすることもできます。 

私の役割では、お客様が最適なビジネス目標セットに対処するための最適な技術ソリューションをお客様に提供できるように支援することに重点を置いています。 公式に、Id、セキュリティ、プライバシー、コンプライアンスに重点を置いています。 これらの操作によってすべての処理が行われていることが大好きです。 これにより、ほとんどのプロジェクトに関係する機会が得られます。 これにより、非常に忙しくてこの役割を楽しんでいます。 

私は、ニューヨーク市 (最高のもの) で住んでおり、文化、食品、人物の多様性 (トラフィックではない) を楽しんでいます。 世界の大部分をライフサイクルでいつでも見ることができるようになると、出張したいと思っています。 現時点では、wildlife について学ぶためにアフリカへの旅を研究しています。

## <a name="guiding-principles"></a>指針原則 

- **シンプルなのは、多く**の場合、テクノロジを使用した方が便利です。 そうではないことを意味します。 特に、セキュリティ領域では、多くのお客様がソリューションをオーバーエンジニアリングしています。 この[ビデオ](https://www.youtube.com/watch?v=SOQgABDSYZE)は、Google のストライプ会議から、この点をアンダスコアとしています。
- **人材、プロセス、テクノロジ**—技術者ではなく、プロセスを強化する[ユーザー向けに設計](https://en.wikipedia.org/wiki/Human-centered_design)されています。 "完全な" ソリューションはありません。 さまざまなリスク要因のバランスを取る必要があり、ビジネスごとに決定が異なります。 ユーザーが後で回避する方法を設計している顧客が多すぎます。
- **後で「理由」および「方法」に注目**してください。たとえば、100万を与える質問を使用して、厄介な7年間の昔の子供になることができます。 適切な質問がわからない場合は、適切な回答に到達できません。 多くのお客様は、ビジネス上の問題を定義するのではなく、どのように動作する必要があるかを前提としています。 取得可能なパスは常に複数存在します。
- **過去のベストプラクティスの長いテール**—ベストプラクティスがライトスピードで変化していることを認識します。 3か月以上前に Azure AD を参照していた場合は、最新の状態ではない可能性があります。 ここに記載されている内容は、公開後に変更される可能性があります。 今日の "Best" オプションは、今から6か月でなければなりません。

## <a name="baseline-concepts"></a>ベースラインの概念

このセクションはスキップしないでください。 数年にクラウドサービスを使用しているお客様にとっても、これらのトピックに戻る必要があることがよくあります。
ああ、言語は正確なツールではありません。 多くの場合、同じ単語を使用して、さまざまな概念や単語が同じ概念を意味していることを意味します。 多くの場合、次の図を使用して、いくつかのベースラインの用語と "階層モデル" を確立します。
<br><br>

![テナント、サブスクリプション、サービス、データの図](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)  

<br>

スイムについて学習する場合は、海上の途中ではなくプールで開始することをお勧めします。 この図は技術的に正確ではありません。 これは、いくつかの基本的な概念について話し合うモデルです。 

図の説明
- テナント = Azure AD のインスタンス。 階層の "上位"、またはダイアグラムのレベル1になります。 これは、他のすべてが行われる "[境界](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-directory-independence)" ([Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)を除く) と考えることができます。 すべての Microsoft enterprise cloud サービスは、これらのテナントの1つに含まれています。 コンシューマーサービスは独立しています。 ドキュメントには、"テナント" が Office 365 テナント、Azure テナント、WVD テナントなどとして表示されます。多くの場合、これらのバリエーションは顧客に混乱を招きます。
- サービス/サブスクリプション、図のレベル2は、1つのテナントにのみ属します。 ほとんどの SaaS サービスは1:1 で、移行せずに移動することはできません。 Azure は異なりますが、[課金](https://docs.microsoft.com/azure/cost-management-billing/manage/billing-subscription-transfer)または[サブスクリプション](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory)を別のテナントに移動することができます。 Azure サブスクリプションを移動する必要があるお客様が多数存在します。 これにはさまざまな意味があります。 サブスクリプションの外部に存在するオブジェクト (たとえば、グループ、アプリ、ポリシーなどを含む RBAC や Azure AD オブジェクトなど) は移動しません。 また、一部のサービス (Azure Key Vault、データブリックなど) は、機能しない状態で移動します。 適切なビジネスニーズを伴わずにサービスを移行しないでください。 移行に役立つスクリプトには、 [GitHub で共有](https://github.com/lwajswaj/azure-tenant-migration)されているものがあります。 
- 通常、特定のサービスには、いくつかの種類の "サブレベル" 境界またはレベル 3 (L3) があります。 これは、セキュリティ、ポリシー、ガバナンスなどの分離を理解するのに役立ちます。残念ながら、理解しているという名前の統一された名前はありません。 L3 の名前の例は、次のとおりです。 Azure Subscription = [resource](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resources-portal);Dynamics 365 CE =[インスタンス](https://docs.microsoft.com/dynamics365/admin/new-instance-management);Power BI = [workspace](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces);電源アプリ =[環境](https://docs.microsoft.com/power-platform/admin/environments-overview)。いう.
- レベル4は、実際のデータがどこに存在するかを示します。 この ' データプレーン ' は複雑なトピックです。 一部のサービスは、RBAC 用に Azure AD を使用していますが、そうではありません。 ここでは、委任のトピックについて説明します。

多くのお客様 (および Microsoft の従業員) については、次の内容についてよくわからないようになっています。


- すべてのユーザーが[無料](https://azure.microsoft.com/pricing/details/active-directory/)で多数のテナントを[作成](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)できます。 その中でサービスをプロビジョニングする必要はありません。 数十。 各テナント名は、Microsoft のワールドワイドクラウドサービスで一意です (つまり、2つのテナントに同じ名前を付けることはできません)。 これらのすべては TenantName.onmicrosoft.com の形式になっています。 テナントを自動的に作成するプロセス ([非管理対象テナント](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup)) もあります。 たとえば、他のテナントに存在しない電子メールドメインを持つエンタープライズサービスに対してユーザーがサインアップした場合に、この現象が発生することがあります。 
- 管理されたテナントでは、多くの[DNS ドメイン](https://docs.microsoft.com/azure/active-directory/fundamentals/add-custom-domain)を登録できます。 これにより、元のテナント名が変更されることはありません。 現時点では、テナント (移行以外) の名前を変更する簡単な方法はありません。 このような場合、テナント名は技術的には重要ではありませんが、制限されていると考えられる場合があります。
- まだサービスの展開を計画していない場合でも、組織のテナント名を予約する必要があります。 そうしないと、ユーザーは自分からそのファイルを受け取ることができ、元に戻す簡単なプロセスはありません (DNS 名と同じ問題が発生します)。 この方法はお客様からよく寄せられています。 テナント名についても、議論のトピックについて説明します。
- DNS 名前空間を所有している場合は、これらすべてをテナントに追加する必要があります。 それ以外の場合は、この名前を使用して管理されていない[テナント](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup)を作成し、[それが管理](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)されるのを停止させることができます。
- DNS 名前空間 (contoso.com など) は、1つのテナントにのみ属することができます。 これはさまざまなシナリオに対して意味があります (たとえば、合併や買収の際に電子メールドメインを共有するなど)。DNS サブ (div.contoso.com など) を別のテナントに登録する方法はありますが、これは避けてください。 トップレベルのドメイン名を登録すると、すべてのサブドメインが同じテナントに属していると見なされます。 マルチテナントのシナリオ (以下を参照) では、通常は別のトップレベルドメイン名 (contoso.ch または ch-contoso.com など) を使用することをお勧めします。
- 誰がテナントを "所有する" 必要があるか。 現在、自分のテナントを所有しているユーザーを知らないお客様がいることがよくあります。 これは大きい赤のフラグです。 すぐに Microsoft サポートに連絡します。 問題があるのと同様に、サービス所有者 (多くの場合、Exchange 管理者) がテナントを管理するように指定されています。 テナントには、今後必要になる可能性があるすべてのサービスが含まれます。 テナント所有者は、組織内のすべてのクラウドサービスの有効化を決定できるグループである必要があります。 別の問題として、テナント所有者グループにすべてのサービスを管理するよう求められた場合があります。 これは大規模な組織にはスケーリングされません。
- サブ/スーパーテナントの概念はありません。 何らかの理由で、この神話は自動的に繰り返され続けます。 これは、 [AZURE AD B2C](https://docs.microsoft.com/azure/active-directory-b2c/)テナントにも適用されます。 「自分の B2C 環境が XYZ テナントにある」または「Azure テナントを Office 365 テナントに移行する方法」または何度も聞こえない場合があります。
- このドキュメントは、ほとんどのお客様が使用しているように、主にコマーシャルの世界規模のクラウドに重点を置いています。 [独立クラウド](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud)について理解しておくと役に立つ場合があります。 独立の雲には、この説明の対象外であることを説明するための追加の影響があります。


## <a name="baseline-identity-topics"></a>ベースラインの id のトピック

Microsoft の identity platform – Azure Active Directory (Azure AD) について多くのドキュメントがあります。 開始しているユーザーにとって、多くの場合、圧倒的な感じがあります。 これについて学習した後でも、絶えず革新と変化を続けることが難しくなる可能性があります。 お客様の対話では、多くの場合、ビジネス上の目標と、これらのトピックに関する人間の「崖メモ」に対処するための "良い、良い、良い、ベスト" の方法について説明しています。 完全な答えはほとんどありませんが、"正しい" 判断はさまざまなリスク要因のバランスになります。 次に、よく寄せられる質問と混乱の分野について、お客様と話し合う傾向があります。

### <a name="provisioning"></a>プロビジョニング
Azure AD では、identity world でのガバナンスがないことは解決されません。 [Id ガバナンス](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)は、クラウドの決定に依存しない重要な要素である必要があります。 ガバナンス要件は、時間の経過と共に変化します。これは、プログラムであり、ツールではありません。 

[AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)と[Microsoft Identity Manager](https://docs.microsoft.com/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) の対比 (サードパーティまたはカスタム)? 今すぐに、また、今後は Azure AD Connect を使用して、多くの頭痛をするようにしてください。 このツールには、特別なお客様の構成や継続的な革新性に対処するためのすべての種類の smarts があります。 

より複雑なアーキテクチャになる可能性があるエッジケースを次に示します。
- これらの間のネットワーク接続がない複数の AD フォレストがあります。 [クラウドプロビジョニング](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning)と呼ばれる新しいオプションがあります。
- Active Directory がありません。また、インストールする必要もありません。 Azure AD Connect は[LDAP から同期](https://docs.microsoft.com/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison)するように構成できます (パートナーが必要になる場合があります)。
- 複数のテナントに同じオブジェクトをプロビジョニングする必要があります。 これは技術的にはサポートされていませんが、"同じ" の定義に依存しています。

既定の同期ルール ([フィルターオブジェクト](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering)、[変更属性](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)、[代替ログイン ID](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-userprincipalname)など) をカスタマイズする必要がありますか。 避けてください。 Id プラットフォームは、それを使用するサービスと同じ価値があります。 すべての種類の nutty 構成を行うことができますが、この質問に答えるには、アプリケーションへの影響を確認する必要があります。 メールが有効なオブジェクトにフィルターを適用すると、オンラインサービスの GAL が不完全になります。アプリケーションが特定の属性に依存している場合、これらのフィルター処理は予測できない影響を与えます。いう.Id チームの決定ではありません。

XYZ SaaS はジャストインタイム (JIT) プロビジョニングをサポートしていますが、同期が必要なのはなぜですか? 上記を参照してください。 多くのアプリケーションには、機能の "プロファイル" 情報が必要です。 メールが有効なすべてのオブジェクトが使用できない場合、GAL を使用することはできません。 Azure AD と統合されたアプリケーションでの[ユーザープロビジョニング](https://docs.microsoft.com/azure/active-directory/app-provisioning/user-provisioning)にも同様です。


### <a name="authentication"></a>認証

[パスワードハッシュ同期](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)(phs) と、[パススルー認証](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-how-it-works)(pta) 対[フェデレーション](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility)。

通常は、フェデレーションに関して熱心な[議論](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn)があります。 通常は単純な方が望ましいため、適切な理由がない限り、PHS を使用します。 同じテナント内の異なる DNS ドメインに対して異なる認証方法を構成することもできます。 

一部のお客様は、主にフェデレーション + PHS を有効にします。
- フェデレーションサービスが使用できない場合に、(障害復旧のために)[フォールバック](https://docs.microsoft.com/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync)するオプション。
- その他の機能 (例: [AZURE AD DS](https://docs.microsoft.com/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)) とセキュリティサービス (例:[リークした資格情報](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials))
- フェデレーション認証 (例: [Azure Files](https://docs.microsoft.com/azure/storage/files/storage-files-active-directory-overview)) を理解していない azure でのサービスのサポート。

多くの場合、misconceptions を明確にするために、クライアント認証フローを通じてお客様を歩きます。 結果は次の図のようになります。これは、それを取得する対話型プロセスほどよくありません。

:::image type="content" source="../media/solutions-architecture-center/identity-beyond-whiteboard-example.png" alt-text="ホワイトボード会話の例":::

このホワイトボードの図は、セキュリティポリシーが認証要求のフロー内で適用される場所を示しています。 この例では、Active Directory フェデレーションサービス (AD FS) によって適用されるポリシーは最初のサービス要求に適用されますが、以降のサービス要求には適用されません。 これは、少なくとも1つの理由により、セキュリティコントロールをクラウドに移行する理由です。

私たちは、覚えている限り、[シングルサインオン](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)(SSO) の夢を追跡しています。 一部のお客様は、「right」フェデレーション (STS) プロバイダーを選択することによって、これを実現できると考えています。 Azure AD は SSO 機能を[有効](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-sso-deployment)にするのに非常に役立ちますが、STS は不思議ではありません。 重要なアプリケーションにまだ使用されている "従来の" 認証方法が多すぎます。 Azure AD を[パートナーソリューション](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list)で拡張することで、これらのシナリオの多くを解決できます。 SSO は、戦略と移行をいいます。 [アプリケーションの標準に](https://docs.microsoft.com/azure/active-directory/develop/v2-app-types)移行せずに、それを取得することはできません。 このトピックに関連するのは、[パスワード](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)のないパスワードに移行することです。これには、不思議な答えはありません。 

現在、[多要素認証](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)(MFA) は重要です (詳細については[こちら](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984)を参照してください)。 It[ユーザー動作分析](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa)に追加し、一般的なサイバー攻撃の大部分を阻止するソリューションを用意しました。 コンシューマーサービスも、MFA を必要とするように移行しています。 それでも、[最新の認証](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview)方法に移行したくない多くのお客様がまだ会います。 最も大きな引き数は、ユーザーや従来のアプリケーションに影響を与えることです。 場合によっては、Exchange Online のアナウンスされた[変更](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282)をユーザーが移動するのに適したキックオフがあります。 多くの Azure AD[レポート](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication)をお客様がこの移行に役立てることができるようになりました。



### <a name="authorization"></a>Authorization

[ウィキペディア](https://en.wikipedia.org/wiki/Authorization)ごとに、"承認対象" はアクセスポリシーを定義することです。 多くのユーザーは、オブジェクト (ファイル、サービスなど) へのアクセス制御を定義できるようになります。 現在の世界規模の脅威では、この概念は、さまざまな脅威ベクトルに反応してアクセス制御をすばやく調整できる動的なポリシーに急速に進化しています。 たとえば、通常とは異なる場所から銀行口座にアクセスすると、追加の確認手順が表示されます。 これを解決するには、ポリシーそのものではなく、脅威の検出とシグナル関連付けの方法論のエコシステムを考慮する必要があります。

Azure AD のポリシーエンジンは、[条件付きアクセスポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)を使用して実装されます。 このシステムは、さまざまな他の脅威検出システムからの情報に依存して動的な意思決定を行います。 単純なビューは、次の図のようになります。

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-illustration-3.png" alt-text="Azure AD のポリシーエンジン":::

これらのすべての信号を統合すると、次のような動的なポリシーが可能になります。
- デバイスで脅威が検出された場合、データへのアクセスは、ダウンロード機能を使用せずに web に制限されます。
- 非常に大量のデータをダウンロードする場合は、ダウンロードしたすべてのデータが暗号化され、制限されます。
- 管理対象外のデバイスからサービスにアクセスした場合、非常に機密性の高いデータからはブロックされますが、制限されていないデータにアクセスすることはできますが、他の場所にコピーすることはできません。

この拡張された認証定義に同意する場合は、追加のソリューションを実装する必要があります。 どのソリューションを実装するかは、ポリシーの動的な方法と、優先度を設定する必要のある脅威によって決まります。 そのようなシステムの例を次に示します。
- [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/) 
- [Azure Advanced Threat Protection](https://docs.microsoft.com/azure-advanced-threat-protection/) (azure ATP)
- [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) (MICROSOFT defender ATP)
- [Microsoft 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (MICROSOFT 365 ATP)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) (mcas)
- [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide) (MTP)
- [Microsoft Intune](https://docs.microsoft.com/mem/intune/)
- [Microsoft Information Protection](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) (MIP)
- [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/) 

もちろん、Azure AD に加えて、さまざまなサービスやアプリケーションには固有の承認モデルがあります。 これらの一部については、後の「委任」セクションで説明します。

### <a name="audit"></a>監査
Azure AD には[、詳細な監査およびレポート](https://docs.microsoft.com/azure/active-directory/reports-monitoring/)機能があります。 ただし、これは通常、セキュリティ上の決定を行うために必要な情報のソースに過ぎません。 詳細については、「委任」セクションを参照してください。

## <a name="there-is-no-exchange"></a>Exchange がありません

焦らないで下さい！ これは、Exchange が非推奨 (または SharePoint など) になっていることを意味するわけではありません。これはまだコアサービスです。 ここでは、今のところ、テクノロジプロバイダーが複数のサービスのコンポーネントを使用してユーザーエクスペリエンス (UX) を移行していたことを意味しています。 Microsoft 365 では、簡単な例として、電子メールの添付ファイルが SharePoint Online または OneDrive for Business に保存されている "[モダン添付ファイル](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)" が挙げられます。 

:::image type="content" source="../media/solutions-architecture-center/modern-attachments.png" alt-text="メールにファイルを添付する":::


Outlook クライアントを見ると、Exchange だけでなく、この機能の一部として "接続されている" サービスの多くが表示されます。 これには、Azure AD、Microsoft Search、アプリ、プロファイル、コンプライアンス、Office 365 グループが含まれます。 

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png" alt-text="吹き出しを使用した Outlook インターフェイス":::

今後の機能のプレビューに関する[Microsoft 流動的なフレームワーク](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268)についてお読みください。 プレビューでは、Outlook で直接 Teams 会話を読んで、返信することができます。 実際には、 [Teams クライアント](https://products.office.com/microsoft-teams/download-app)はこの戦略のより顕著な例の1つです。 

全体として、Office 365 と Microsoft クラウドの他のサービスとの間に明確な線を描画するのは困難になりつつあります。 お客様にとっては、1つのコンポーネントを使用している場合でも、すべての革新を通じてメリットを得ることができるため、お客様に大きなメリットとして表示されます。 非常にクールで、多くのお客様に対する影響をはるかに上回ります。

今日、多くのお客様は「製品」を中心に構造化されています。 特定の製品ごとに専門家が必要なので、オンプレミスの世界にとっては論理的です。 ただし、これらのサービスがクラウドに移行されると、Active Directory または Exchange データベースを再度デバッグする必要はありません。 自動化 (クラウドの種類がの場合) は、特定の反復的な手動ジョブを削除します (工場に対して何が起こったかを確認します)。 ただし、これらは、サービス間の相互作用、影響、ビジネスニーズなどを理解するためのより複雑な要件に置き換えられました。[学習](https://docs.microsoft.com/learn/)したい場合は、クラウドの変換によって有効になる機会があります。 テクノロジに進む前に、IT スキルとチーム構造の変更を管理することについてお客様に説明します。

すべての SharePoint ファンについては、「SharePoint online で XYZ をどうすればよいですか?」という質問を停止してください。 ワークフローの[パワー自動](https://docs.microsoft.com/power-automate/)処理 (別名) を使用すると、より強力なプラットフォームとなります。 [Azure Bot フレームワーク](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0)を使用して、500K item リストにより良い UX を作成します。 CSOM の代わりに[Microsoft Graph](https://developer.microsoft.com/graph/)の使用を開始します。 [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)には、SharePoint が含まれていますが、その他の世界もあります。 他にも多数の例が挙げられています。 非常にすばらしい専門分野があります。 ドアを開き、[探索] を[開始](https://docs.microsoft.com)します。

その他の一般的な影響は、[コンプライアンス] 領域にあります。 このクロスサービスアプローチでは、多くのコンプライアンスポリシーが完全に混同されているように見えます。 「電子情報開示システムへのすべての電子メール通信をジャーナル処理する必要がある」という状態の組織を常に把握しています。 これは、電子メールが電子メールだけでなく、他のサービスにウィンドウを表示しない場合にどのような意味がありますか。 Office 365 には、[コンプライアンス](https://docs.microsoft.com/microsoft-365/compliance/)のための包括的な手法がありますが、ユーザーとプロセスの変更はテクノロジよりもはるかに難しいことがあります。

他にも多くの人とプロセスに影響があります。 ご意見をお持ちの場合、これは重要な議論の領域です。 他の記事では、さらに多くのことがあります。

## <a name="tenant-structure-options"></a>テナント構造オプション

### <a name="single-tenant-vs-multi-tenant"></a>1つのテナントとマルチテナントの比較

一般に、ほとんどのお客様は1つの運用テナントのみを持つ必要があります。 複数のテナントが困難である ( [Bing search](https://www.bing.com/search?q=office%20365%20multiple%20tenants)を提供する)、またはこの[ホワイトペーパー](https://aka.ms/multi-tenant-user)を読み取っている理由はたくさんあります。 同時に、多くの企業のお客様が IT 学習、テスト、および実験のために別の (小規模な) テナントを使用しています。 [Azure Lighthouse](https://azure.microsoft.com/services/azure-lighthouse/)を使用すると、テナント間の azure アクセスが容易になります。 Office 365 と他の多くの SaaS サービスでは、クロステナントのシナリオに制限があります。 [AZURE AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)シナリオでは、多くのことを考慮する必要があります。

多くのお客様は、合併と買収 (M&A) を行った後に複数の運用テナントを使用して、統合を行うことができます。 今日では、これは簡単ではないため、Microsoft コンサルティングサービス (MCS) またはパートナーとサードパーティ製のソフトウェアが必要になります。 今後、複数のテナントを使用しているお客様のさまざまなシナリオに対応するために、継続的なエンジニアリング作業が行われています。 

ユーザーによっては、複数のテナントを使用することを選択する場合があります。 これは非常に慎重な決定であり、ほとんどの場合、ビジネス上の理由に基づいています。 次に例を示します。
- さまざまなエンティティ間のコラボレーションを容易にする必要がなく、管理やその他の分離が必要とされる、持株の種類の会社構造。
- 購入後、2つのエンティティを別々に保持するためのビジネス上の決定が行われます。
- お客様の環境をシミュレーションします。お客様の本番環境は変更されません。 
- お客様向けのソフトウェアの開発。

これらのマルチテナントのシナリオでは、多くの場合、テナント間でいくつかの構成を維持するか、構成の変更と drifts を報告します。 これは、多くの場合、手動による変更から、コードとしての構成への移行を意味します。 Microsoft Premiere サポートは、このパブリック IP に基づくこれらの種類の要件につい[https://Microsoft365dsc.com](https://Microsoft365dsc.com)てワークショップを提供します。


### <a name="multi-geo"></a>Multi-Geo 

複数[地域に](https://docs.microsoft.com/office365/enterprise/office-365-multi-geo)する場合、または複数地域にしない場合は、この質問が該当します。 Office 365 複数地域を使用すると、[データ常駐](https://docs.microsoft.com/office365/enterprise/o365-data-locations)の要件を満たすように選択した地理的な場所に、保存データをプロビジョニングして保存することができます。 この機能については、多くの misconceptions があります。 以下の点にご注意ください。 
- パフォーマンス上のメリットは提供されません。 [ネットワーク設計](https://aka.ms/office365networking)が適切でない場合は、パフォーマンスが悪くなる可能性があります。 Microsoft ネットワークに対して "閉じる" デバイスを取得する (必ずしもデータには使用しないでください)。
- [GDPR コンプライアンス](https://www.microsoft.com/trust-center/privacy/gdpr-overview)のソリューションではありません。 GDPR は、データ主権または保存場所にフォーカスしません。 そのためのコンプライアンスフレームワークは他にもあります。
- この方法では、管理の委任 (下の図を参照) または[情報バリア](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)は解決されません。
- マルチテナントとは異なり、追加の[ユーザープロビジョニング](https:/docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation)ワークフローが必要です。
- テナント (Azure AD) は別の地域に[移動](https://docs.microsoft.com/office365/enterprise/moving-data-to-new-datacenter-geos)しません。 

## <a name="delegation-of-administration"></a>管理の委任

ほとんどの大規模な組織では、職務と役割ベースのアクセス制御 (RBAC) の分離が必要になります。 前もって、もう一度お詫びになる予定です。 これは、お客様が希望するほど簡単ではありません。 顧客、法律、コンプライアンス、およびその他の要件は異なり、世界中で競合する場合があります。 簡略化と柔軟性は、多くの場合、互いの反対側にあります。 間違いなく、この時点でより良いジョブを実行できます。 時間の経過とともに、大幅な改善が行われています。 379230のドキュメントを読むことなく、ビジネス要件に適合するモデルを解決するには、お住まいの地域の[Microsoft テクノロジセンター](https://www.microsoft.com/mtc)を参照してください。 ここでは、考慮すべきことについて説明します。 ここでは、計画する5つの異なる領域と、よく寄せられる質問の一部を示します。

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Azure AD と Microsoft 365 管理センター

長く、[組み込みの役割](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)の一覧があります。 各役割は、グループ化された役割権限のリストで構成され、特定のアクションを実行できます。 これらのアクセス許可は、各役割内の [説明] タブで確認できます。 または、Microsoft 365 管理センターで、より人間が読みやすいバージョンを表示することもできます。 組み込みのロールの定義を変更することはできません。 一般的には、これらを次の3つのカテゴリにグループ化します。

- **全体管理者**—他のシステムの場合と同じように、この "すべての強力な" 役割を[高度に保護](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)する必要があります。 一般的な推奨事項は次のとおりです。永続的な割り当てはありません。また、Azure AD 特権 Id 管理 (PIM) を使用します。強力な認証。いう.興味深いことに、この役割では既定ですべてのものにアクセスできません。 通常、コンプライアンスアクセスと Azure アクセスに関しては、後で説明するような混乱が見られます。 ただし、この役割では、テナント内の他のサービスへのアクセスをいつでも割り当てることができます。 
- **特定のサービス管理者**—一部のサービス (Exchange、SharePoint、Power BI など) は、Azure AD からの高レベルの管理役割を使用します。 これは、すべてのサービスで一貫したものではなく、後で説明するサービス固有の役割もあります。
- **機能**します。特定の操作 (ゲスト招待元など) に焦点を合わせた、長い (または増加した) 役割の一覧があります。 これらの多くは、お客様のニーズに基づいて追加されています。

すべてを委任することはできません (ただし、ギャップは減少します)。つまり、グローバル管理者の役割を使用する必要がある場合があります。 この役割のメンバーではなく、コードとしての構成と自動化を考慮する必要があります。

**注**: Microsoft 365 管理センターには、ユーザーフレンドリなインターフェイスがありますが、Azure AD 管理者の環境と比較して機能のサブセットがあります。 両方のポータルは同じ Azure AD の役割を使用するので、変更は同じ場所で行われます。 ヒント: Azure の低優先管理 UI をすべて非表示にしたい場合は、を[https://aad.portal.azure.com](https://aad.portal.azure.com)使用します。 

名前の種類 役割の名前から仮定しないでください。 言語は、非常に正確なツールではありません。 目標は、必要な役割を確認する前に委任する必要がある操作を定義することです。 "Security Reader" 役割に他のユーザーを追加しても、すべてのユーザーのセキュリティ設定が表示されることはありません。 

[カスタムロール](https://docs.microsoft.com/azure/active-directory/users-groups-roles/roles-custom-overview)を作成する機能は、よくある質問です。 これは、Azure AD では現在制限されています (以下を参照)。ただし、時間の経過とともに機能が拡張されます。 これらは Azure AD の関数に適用できると考えていますが、階層モデル (前述) には含まれていない場合があります。 「Custom」を使用している場合は、「シンプルな」のプリンシパルに戻る傾向があります。

もう1つの一般的な質問は、役割のスコープをディレクトリのサブセットにすることです。 一例としては、「EU のユーザー向けのヘルプデスク管理者のみ」のようなものがあります。 [管理単位](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-administrative-units)(AU) は、これに対処することを目的としています。 前述のように、これらは Azure AD の機能に適用可能と考えられ、"down" にまたがることはありません。 当然ですが、特定の役割では、範囲を設定することには意味がありません (グローバル管理者、サービス管理者など)。

現在、これらのすべての役割には直接メンバーシップが必要です ( [AZURE AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/)を使用する場合は動的割り当て)。 これは、ユーザーが Azure AD でこれらを直接管理する必要があり、セキュリティグループのメンバーシップに基づくことはできません。 これは、管理者特権で実行する必要があるので、スクリプトを作成して管理するファンではありません。 通常は、ServiceNow のようなプロセスシステムとの API の統合、または Savi/t のようなパートナーガバナンスツールの使用をお勧めします。 この時間をかけて、これに対処するためのエンジニアリング作業が行われています。

[AZURE AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/)については、何度も説明してきました。 オンプレミスのコントロールには、対応する Microsoft Identity Manager (MIM)[特権アクセス管理](https://docs.microsoft.com/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services)(PAM) ソリューションがあります。 また、権限のある[アクセスワークステーション](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations)(PAWs) と[Azure AD Identity ガバナンス](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)についても確認する必要があります。 さまざまなサードパーティ製のツールがあります。これにより、ジャストインタイムでだけでなく、動的な役割昇格を有効にすることもできます。 これは通常、環境を保護するためのより大きな討議の一部です。 

場合によっては、外部ユーザーをロールに追加することをお問い合わせください (上記のマルチテナントセクションを参照)。 これは問題なく機能します。 [AZURE AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/)はもう1つの大きなトピックで、お客様を紹介しています。別の記事を参照してください。

### <a name="security-and-compliance-center-scc"></a>セキュリティ/コンプライアンスセンター (SCC)

[Office 365 セキュリティ & コンプライアンスセンターでのアクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)は、「役割グループ」のコレクションです。これは、Azure AD の役割とは別のもので、別個のものです。 これらの役割グループの中には、Azure AD の役割 (たとえば、セキュリティリーダー) と同じ名前を持つものがありますが、メンバーシップが異なる場合があるため、これはわかりにくい場合があります。 Azure AD の役割の使用を希望しています。 各役割グループは、1つ以上の "役割" で構成されています (同じ単語を再利用する意味を参照してください)。また、電子メールが有効なオブジェクトである Azure AD のメンバーを持っている必要があります。 また、役割と同じ名前を持つ役割グループを作成することもできます (この役割を含めることができない場合があります)。

意味では、これらは Exchange 役割グループモデルの進化です。 ただし、Exchange Online には、独自の[役割グループの管理](https://docs.microsoft.com/exchange/permissions-exo)インターフェイスがあります。 Exchange Online の一部の役割グループは、Azure AD またはセキュリティ & コンプライアンスセンターからロックおよび管理されますが、その他は同じまたは類似した名前であり、Exchange Online で管理されている場合があります (混乱に追加されます)。 Exchange 管理のためのスコープが必要でない限り、Exchange Online のユーザーインターフェイスを使用しないことをお勧めします。

カスタムロールを作成することはできません。 役割は、Microsoft によって作成されたサービスによって定義され、新しいサービスが導入されるにつれて拡張されます。 これは、Azure AD の[アプリケーションによって定義されたロール](https://docs.microsoft.com/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps)と概念が似ています。 新しいサービスが有効になっている場合、多くの場合、これらのアクセス権を付与または委任するために、新しい役割グループを作成する必要があります (例: [insider リスク管理](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure?view=o365-worldwide#step-1-required-enable-permissions-for-insider-risk-management))。

これらの役割グループには直接メンバーシップも必要であり、Azure AD グループを含めることはできません。 しかし、現時点では、これらの役割グループは Azure AD PIM ではサポートされていません。 Azure AD の役割と同様に、これらの管理を Api で管理するか、またはその他のパートナーガバナンス製品として使用することをお勧めします。

セキュリティ & コンプライアンスセンターの役割には、Microsoft 365 が含まれており、これらの役割グループを環境のサブセット (Azure AD の管理単位の場合など) にスコープすることはできません。 多くのお客様は、サブ委任の方法を尋ねています。 たとえば、「EU ユーザーにのみ DLP ポリシーを作成する」というようにします。 現在、セキュリティ & コンプライアンスセンターの特定の機能に対する権限を持っている場合は、テナント内のこの関数に含まれるすべての権限を持つことになります。 しかし、多くのポリシーには、環境のサブセットを対象とする機能があります (たとえば、[これらの[ラベル](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy)をこれらのユーザーにのみ使用できるようにする])。 適切なガバナンスとコミュニケーションは、競合を回避する主要なコンポーネントです。 お客様によっては、セキュリティ & コンプライアンスセンターでのサブ委任のアドレス設定を実装することを選択しています。 一部の特定のサービスは、サブ委任をサポートしています (以下を参照)。 

セキュリティ & コンプライアンスセンター (protection.office.com) を介して現在管理されている統制は、2つの個別の管理ポータルに移行する必要があることに注意してください。 security.microsoft.com と compliance.microsoft.com。 変更は唯一の定数です。

### <a name="service-specific"></a>サービス固有

前述したように、多くのお客様は、より詳細な委任モデルを実現することを望んでいます。 一般的な例として、"部署 X のユーザーと場所に対して XYZ サービスのみを管理する" (またはその他の次元) があります。 この操作を実行できるかどうかは、各サービスによって異なり、サービスや機能の間で一貫していません。 さらに、各サービスに個別の一意の RBAC モデルがある場合があります。 これらのすべてについて説明するのではなく、各サービスに関連するリンクを追加しています。 これは完全なリストではありませんが、開始することになります。

- **Exchange Online** - [https://docs.microsoft.com/exchange/permissions-exo/permissions-exo](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- **SharePoint Online** - [https://docs.microsoft.com/sharepoint/manage-site-collection-administrators](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators) 
- **Microsoft**  -  [ Teamshttps://docs.microsoft.com/microsoftteams/itadmin-readiness](https://docs.microsoft.com/microsoftteams/itadmin-readiness )
- **情報** - [https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions](https://docs.microsoft.com/microsoft-365/compliance/) 
  + **アクセス許可のフィルター処理** -  [ https://docs.microsoft.com/microsoft-365/compliance/permissions-filtering-for-content-search](https://docs.microsoft.com/microsoft-365/compliance/)
  + **コンプライアンスの境界** -  [ https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries )
  + **高度な電子情報開示** -  [ https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 )
- **Yammer** - [https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins) 
- **複数地域** - [https://docs.microsoft.com/office365/enterprise/add-a-sharepoint-geo-admin](https://docs.microsoft.com/office365/enterprise/add-a-sharepoint-geo-admin) 
- **Dynamics 365** -[https://docs.microsoft.com/dynamics365/](https://docs.microsoft.com/dynamics365/) <br>
  注: このリンクは、ドキュメントのルートに関連しています。 管理/委任モデルには、さまざまな種類のサービスがあります。
- **電源** -  [プラットフォームhttps://docs.microsoft.com/power-platform/admin/admin-documentation](https://docs.microsoft.com/power-platform/admin/admin-documentation )
  + **パワー**  -  [アプリhttps://docs.microsoft.com/power-platform/admin/wp-security](https://docs.microsoft.com/power-platform/admin/wp-security ) <br>
    注: 管理/委任モデルにはバリエーションがある複数の種類があります。
  + **電源の自動化** -  [ https://docs.microsoft.com/power-automate/environments-overview-admin](https://docs.microsoft.com/power-automate/environments-overview-admin )
  + **PowerBI** -  [ PowerBIhttps://docs.microsoft.com/power-bi/service-admin-governance](https://docs.microsoft.com/power-bi/service-admin-governance ) <br>
メモ: データプラットフォームのセキュリティと委任 (Power BI がコンポーネントである) は、複雑な領域です。
- **MEM/Intune**  -  [ https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control )
- **Microsoft Defender ATP**  -  [ https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles )
- **Microsoft の脅威保護** - [https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions)
- **Microsoft Cloud App Security** - [https://docs.microsoft.com/cloud-app-security/manage-admins](https://docs.microsoft.com/cloud-app-security/manage-admins)
- **Stream** -  [ Streamhttps://docs.microsoft.com/stream/assign-administrator-user-role](https://docs.microsoft.com/stream/assign-administrator-user-role )
- **情報の障壁** -  [ https://docs.microsoft.com/microsoft-365/compliance/information-barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers )

Rest に関しては、ドキュメント内の検索は最近有効[https://docs.microsoft.com/](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)になっています。 


### <a name="activity-logs"></a>アクティビティログ
Office 365 には、[統合監査ログ](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)があります。 これは非常に[詳細なログ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)ですが、名前にはあまり目を通しないでください。 セキュリティおよびコンプライアンスに必要なすべての情報が含まれているわけではありません。 また、[高度な監査](https://docs.microsoft.com/microsoft-365/compliance/advanced-audit)に関心をお持ちのお客様もいます。 

他の API を通じてアクセスされる Microsoft 365 ログの例には、次のようなものがあります。
- [AZURE AD](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-settings) (Office 365 に関連付けられていないアクティビティ)
- [Exchange メッセージ追跡](https://docs.microsoft.com/powershell/module/exchange/mail-flow/get-messagetrace?view=exchange-ps)
- 前述の脅威/UEBA システム (たとえば、Azure AD Identity Protection、Microsoft Cloud App Security、Microsoft Defender ATP など)
- [Microsoft information protection](https://docs.microsoft.com/microsoft-365/compliance/data-classification-activity-explorer?view=o365-worldwide)
- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

最初に、セキュリティおよびコンプライアンスプログラムに必要なすべてのログソースを特定することが重要です。 また、ログごとに、オンラインの保存期間の制限が異なることにも注意してください。 

管理委任の観点から見ると、Microsoft のほとんどの365アクティビティログには、組み込みの RBAC モデルは含まれていません。 ログを表示するためのアクセス許可がある場合は、その中にすべての情報が表示されます。 顧客要件の一般的な例としては、「EU ユーザーのアクティビティのみを照会できるようにする (またはその他の次元)」などがあります。 この要件を満たすには、ログを別のサービスに転送する必要があります。 Microsoft クラウドでは、 [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)または[ログ分析](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)のいずれかに転送することをお勧めします。 

高レベルの図:

![ログフローの高レベルの図](../media/solutions-architecture-center/identity-beyond-illustration-4.png)  

上記の図は、イベントハブや Azure ストレージ、または Azure ログ分析にログを送信する組み込みの機能を示しています。 このまますぐに使えるすべてのシステムが含まれるわけではありません。 しかし、これらのログを同じリポジトリに送信する方法は他にもあります。 例については、「 [Teams を Azure Sentinel で保護](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761)する」を参照してください。

すべてのログを1つのストレージの場所にまとめることには、相互関係、カスタム保存期間、RBAC モデルをサポートするために必要なデータを補強するなどの利点が追加されます。データがこのストレージシステムに格納されると、適切な RBAC モデルを使用して PowerBI ダッシュボード (または別の種類の視覚エフェクト) を作成できます。

ログを1か所のみに指示する必要はありません。 また、 [POWER BI](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics?view=o365-worldwide)の Microsoft Cloud App Security またはカスタムの RBAC モデル[に Office 365 ログ](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)を統合することが有益な場合もあります。 さまざまなリポジトリには、さまざまな利点と対象ユーザーがあります。

[Microsoft の脅威保護](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)と呼ばれるサービスには、セキュリティ、脅威、脆弱性などに対して豊富な機能が組み込まれていることに注意してください。

多くの大規模なお客様は、このログデータをサードパーティ製システム (たとえば、SIEM) に転送することを希望しています。 この方法にはさまざまな方法がありますが、一般的な[Azure イベントハブ](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs)および[グラフ](https://docs.microsoft.com/graph/security-integration)は、開始点としては適しています。


### <a name="azure"></a>Azure 
高度な特権の役割を Azure AD、Azure、および SaaS の間で分ける方法があるかどうか (例: Azure 365 ではなく、Azure ではない) を確認する必要があります。  いやそうではありません。  マルチテナントアーキテクチャが必要なのは、完全な管理上の分離が必要[complexity](https://aka.ms/multi-tenant-user)な場合です。 これらのサービスはすべて、同じセキュリティ/id の境界に含まれています (上記の階層モデルを参照してください)。  

同じテナント内のさまざまなサービス間の関係を理解することが重要です。 Azure、Office 365、および電源プラットフォームにまたがるビジネスソリューションを構築する多くのお客様と連携しています (多くの場合、オンプレミスおよびサードパーティのクラウドサービスも対象としています)。 1つの一般的な例を次に示します。 
-   一連のドキュメント/画像などに対して共同作業を行う (Office 365)
-   承認プロセスを使用して、それぞれの1つを送信する (パワープラットフォーム)
-   すべてのコンポーネントが承認されると、これらを統合された成果物 (Azure) [Microsoft GRAPH API](https://docs.microsoft.com/azure/active-directory/develop/microsoft-graph-intro)にまとめることができます。  これは不可能ですが、[複数のテナント](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)にまたがるソリューションを設計することは非常に複雑です。

Azure の役割ベースのアクセス制御 (RBAC) により、Azure の詳細なアクセス管理が可能になります。 RBAC を使用すると、ユーザーがジョブを実行するのに必要な最小限のアクセス許可を付与することで、リソースへのアクセスを管理できます。 詳細はこのドキュメントの範囲外ですが、RBAC の詳細については、「 [Azure での役割ベースのアクセス制御 (rbac) とは](https://docs.microsoft.com/azure/role-based-access-control/overview)」を参照してください。 RBAC は重要ですが、Azure のガバナンスに関する考慮事項の一部にすぎません。 詳細については、「[クラウド導入フレームワーク](https://docs.microsoft.com/azure/cloud-adoption-framework/govern/)」を参照してください。 私の友人、Andres Ravinet は、お客様が方法を決定するためにさまざまなコンポーネントについてのステップバイステップで説明しています。 さまざまな要素の高レベルのビュー (実際の顧客モデルに到達するプロセスとしては適していません) は、次のようなものです。

:::image type="content" source="../media/solutions-architecture-center/identity-beyond-illustration-5.png" alt-text="委任された管理のための Azure コンポーネントの高レベルのビュー":::

上記の図からわかるように、他の多くのサービスは設計の一部として考慮する必要があります (例: [Azure ポリシー](https://docs.microsoft.com/azure/governance/policy/overview)、 [asure 青写真](https://docs.microsoft.com/azure/governance/blueprints/overview)、[管理グループ](https://docs.microsoft.com/azure/governance/management-groups/)など)。

## <a name="conclusion"></a>結論
短時間の概要として開始されましたが、予想よりも長くなっています。  これで、組織の委任モデルの作成の詳細を紹介する準備ができました。  この会話は、お客様とよく似ています。 すべてのユーザーに対して動作するモデルは1つありません。 お客様に対して表示される一般的なパターンを文書化する前に、Microsoft エンジニアリングからいくつかの改善された改良を待ってください。 それまでは、Microsoft アカウントチームと協力して、最も近い[Microsoft テクノロジセンター](https://www.microsoft.com/mtc)へのアクセスを手配することができます。  こちらを参照してください。


