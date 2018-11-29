---
title: 共通の id とデバイスのアクセス ポリシーの Microsoft 365 エンタープライズ |マイクロソフトのドキュメント
description: ID およびデバイス アクセス ポリシーと構成を適用する方法に関する Microsoft の推奨事項のポリシーを説明します。
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 72a957222ed3bba449e1576873bfc87a614c075b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869634"
---
# <a name="common-identity-and-device-access-policies"></a>共通 ID とデバイスのアクセス ポリシー
この資料では、Azure AD アプリケーション プロキシを使用してなどの設置型のアプリケーションが公開されたクラウド サービスへのアクセスをセキュリティで保護するためのポリシーをお勧めする一般的なを説明します。 

このガイダンスでは、新しくプロビジョニングした環境に推奨されるポリシーを展開する方法について説明します。 別のラボ環境でこれらのポリシーを設定することで、実稼働前環境と実稼働環境に段階的にロールアウトする前に推奨されるポリシーを理解して評価することができます。 新しくプロビジョニングされた環境はクラウド専用またはハイブリッドである場合があります。  

## <a name="policy-set"></a>ポリシーの設定 

次の図は、推奨される一連のポリシーを示しています。保護のためのどの層は、各ポリシーが適用され、Pc、電話、タブレット、またはデバイスの両方のカテゴリに、ポリシーを適用するかどうかを示しています。これらのポリシーが構成されていることも示しています。

![Id とデバイスのアクセスを構成するための共通のポリシー](../images/Identity_device_access_policies_byplan.png)


この資料の残りの部分では、これらのポリシーを構成する方法について説明します。 

Intune に確実に目的のユーザーの所有していることには、デバイスのデバイスを登録する前に、多要素認証を使用することをお勧めします。Intune にデバイスのコンプライアンス ・ ポリシーを適用する前にデバイスを登録する必要があります。

提供するこれらのタスクを実行する時間を次の表に記載されている順序で、ベースライン ポリシーを実装することをお勧めします。ただし、規制の厳しい機密保護の MFA のポリシーは、いつでも実装できます。


|保護レベル|[Policies]|詳細情報|
|:---------------|:-------|:----------------|
|**基準**|[サインインのリスクが*中*または*高*の場合は、MFA を必要とします。](#require-mfa-based-on-sign-in-risk)| |
|        |[現代の認証をサポートしていないクライアントをブロック](#block-clients-that-dont-support-modern-authentication)|現代の認証を使用しないクライアントは、これらをブロックすることが重要であるため条件付きのアクセス規則をバイパスできます。|
|        |[危険度の高いユーザーがパスワードを変更する必要があります。](#high-risk-users-must-change-password)|自分のアカウントにリスクの高いアクティビティが検出された場合は、サインイン時にパスワードの変更をユーザーに強制します。|
|        |[アプリケーション保護のポリシーを定義します。](#define-app-protection-policies)|プラットフォーム (iOS、Android、Windows) あたり 1 つのポリシーです。|
|        |[承認済みのアプリケーションを必要とします。](#require-approved-apps)|フォンやタブレットのモバイル アプリケーションの保護を適用します。|
|        |[デバイスのコンプライアンス ・ ポリシーを定義します。](#define-device-compliance-policies)|プラットフォームごとに 1 つのポリシーです。|
|        |[準拠の Pc を必要とします。](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Pc の Intune 管理を実施します。|
|**機密**|[サインインのリスクとは、*低*、*中*または*高*の場合は、MFA を必要とします。](#require-mfa-based-on-sign-in-risk)| |
|         |[準拠の Pc*と*モバイル デバイスを必要とします。](#require-compliant-pcs-and-mobile-devices)|Pc と電話とタブレットの Intune 管理が適用されます。|
|**高度な規制**|[*常に*MFA を必要とします。](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>ユーザーにポリシーを割り当てる
ポリシーを構成する前に、保護の各階層を使用している Azure AD グループを識別します。通常、基準計画の保護は、組織の全員に適用されます。ベースラインと機密保護の両方に含まれているユーザーには、適用されるすべてのベースライン ポリシーと機密性の高いポリシーがあります。保護は累積的で、最も制限の厳しいポリシーを適用します。 

Azure AD グループの条件付きアクセスの除外を作成することをお勧めします。「除外」の下の条件付きのアクセス規則のすべてにこのグループを追加します。これは、アクセスに関する問題のトラブルシューティングを行う間、ユーザーにアクセスを提供する方法を示します。一時的なソリューションとしてのみお勧めします。変更するには、このグループを監視し、除外グループが意図したとおりにのみ使用されていることを確認します。 

ユーザーの割り当て] および [除外リストの例を次の図に示します。

![例ユーザーの割り当てと MFA のルールの除外](../images/identity-access-policies-assignment.png)

図は、「トップ シークレット プロジェクト X チーム」には MFA*常に*必要な条件付きのアクセス ポリシーが割り当てられます。ユーザーに高いレベルの保護を適用するときに多用します。このプロジェクト チームのメンバーは、高度規制対象のコンテンツを表示していない場合でも、ログオンするたびに 2 つの形式の認証を提供する必要があります。  

 これらの推奨事項の一部として作成されたすべての Azure AD グループは、Office 365 のグループとして作成する必要があります。これは、SharePoint Online のドキュメントをセキュリティで保護すると、Azure 情報保護 (AIP) の展開で特に重要です。

![Office 365 のグループを作成するための画面キャプチャ](../images/identity-device-AAD-groups.png)




## <a name="require-mfa-based-on-sign-in-risk"></a>サインインのリスクに基づく MFA を必要とします。
MFA を必要とする前に MFA のユーザーを登録するのには、識別情報の保護の MFA の登録ポリシーを使用します。ユーザーが登録された後は、サインインの MFA を適用できます。MFA を持つすべてのユーザーを登録する[作業の前提条件](identity-access-prerequisites.md)が含まれます。

条件付きアクセス ポリシーを作成するには: 

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。 正常にサインインすると、Azure ダッシュボードが開きます。

2. 左側のメニューから **[Azure Active Directory]** を選びます。

3. **[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。

4. 次のスクリーン ショットに示すように、**新しいポリシー**を選択します。

![ベースラインとなる CA ポリシー](./media/secure-email/CA-EXO-policy-1.png)

 次の表では、このポリシーを実装するために条件付きのアクセス ポリシーの設定について説明します。

**割り当て**

|型|[プロパティ]|値|メモ|
|:---|:---------|:-----|:----|
|ユーザーとグループ|含める|ユーザーとグループの選択 – 対象ユーザーを含む特定のセキュリティ グループを選択します|パイロット ユーザーを含むセキュリティ グループから開始します。|
||除外|例外セキュリティ グループ、サービス アカウント (アプリ ID)|必要に応じて一時的にメンバーシップを変更します|
|クラウド アプリ|含める|この規則を適用しアプリケーションを選択します。たとえば、Office 365 Exchange Online を選択します。||
|条件|構成済み|はい|使用環境およびニーズに合わせて構成します|
|サインイン リスク|リスク レベル||次の表のガイダンスを参照してください。|

**サインイン リスク**

対象とする保護レベルの設定を適用します。

|プロパティ|レベルの保護|値|メモ|
|:---|:---------|:-----|:----|
|リスク レベル|基準|高、中|両方をチェック|
| |機密|高、中、低|3 つすべてチェック|
| |高度な規制| |MFA を常に適用するすべてのオプションをオフします。|

**アクセス制御**

|型|[プロパティ]|値|メモ|
|:---|:---------|:-----|:----|
|許可|アクセスの許可|True|オン|
||MFA を要求|True|Check|
||準拠としてマークするデバイスを必要とします。|False||
||ハイブリッド Azure AD の結合に使用したデバイスを必要とします。|False||
||承認されたクライアント アプリケーションを必要とします。|False||
||選択したコントロールすべてが必要|True|オン|

> [!NOTE]
> **を**クリックして、このポリシーを有効にすることを確認します。ポリシーをテストする[場合](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)このツールを使用して検討してください。



## <a name="block-clients-that-dont-support-modern-authentication"></a>現代の認証をサポートしていないクライアントをブロック
1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。 正常にサインインすると、Azure ダッシュボードが開きます。

2. 左側のメニューから **[Azure Active Directory]** を選びます。

3. **[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。

4. **[新しいポリシー]** を選びます。

次の表では、このポリシーを実装するために条件付きのアクセス ポリシーの設定について説明します。

**割り当て**

|型|[プロパティ]|値|メモ|
|:---|:---------|:-----|:----|
|ユーザーとグループ|含める|ユーザーとグループの選択 – 対象ユーザーを含む特定のセキュリティ グループを選択します|パイロット ユーザーを含むセキュリティ グループから開始します。|
||除外|例外セキュリティ グループ、サービス アカウント (アプリ ID)|必要に応じて一時的にメンバーシップを変更します|
|クラウド アプリ|含める|この規則を適用しアプリケーションを選択します。たとえば、Office 365 Exchange Online を選択します。||
|条件|構成済み|はい|クライアント アプリケーションを構成します。|
|クライアント アプリケーション|構成済み|はい|モバイル アプリケーションとデスクトップ クライアント、その他の (両方を選択)|

**アクセス制御**

|型|[プロパティ]|値|メモ|
|:---|:---------|:-----|:----|
|許可|アクセスの禁止|True|オン|
||MFA を要求|False||
||準拠としてマークするデバイスを必要とします。|False||
||ハイブリッド Azure AD の結合に使用したデバイスを必要とします。|False||
||承認されたクライアント アプリケーションを必要とします。|False||
||選択したコントロールすべてが必要|True|オン|

> [!NOTE]
> **を**クリックして、このポリシーを有効にすることを確認します。ポリシーをテストする[場合](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)このツールを使用して検討してください。



## <a name="high-risk-users-must-change-password"></a>危険度の高いユーザーがパスワードを変更する必要があります。
アカウントを侵害されたすべての高リスク ユーザーに、サインイン時に強制的にパスワードを変更させるには、次のポリシーを適用する必要があります。

ログイン、 [Microsoft Azure ポータル (http://portal.azure.com) ](http://portal.azure.com/) 、管理者の資格情報に移動**Azure AD Id 保護 > リスクのポリシーをユーザー**。

**割り当て**

|型|[プロパティ]|値|メモ|
|:---|:---------|:-----|:----|
|Users|含める|[すべてのユーザー]|オン|
||除外|なし||
|条件|ユーザーのリスク|高|オン|

**コントロール**

| 型 | [プロパティ] | 値                  | メモ |
|:-----|:-----------|:------------------------|:------|
|      | アクセス     | SSL 経由でのみ            | True  |
|      | アクセス     | パスワードの変更を必須とする | True  |

**レビュー:** 該当なし

> [!NOTE]
> **を**クリックして、このポリシーを有効にすることを確認します。ポリシーをテストする[場合](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)このツールを使用して検討してください。

## <a name="define-app-protection-policies"></a>アプリケーション保護のポリシーを定義します。
アプリケーション保護ポリシーがどのアプリが許可を定義し、アクションを生かすには、組織のデータ。Intune アプリケーションに、Azure ポータル内からの保護ポリシーを作成します。 

プラットフォームごとにポリシーを作成します。
- iOS
- Android
- Windows 10

新しいアプリケーションの保護ポリシーを作成するのには、管理者の資格情報を使用して、Microsoft Azure ポータルにログインしに移動**モバイル アプリケーション > アプリケーションの保護ポリシー**。**ポリシーの追加**] をクリックします。

アプリケーション保護でわずかな違いポリシー オプションは iOS および Android の間です。Android 用に特別には、ポリシーの下。その他のポリシーのガイドとして使用します。

推奨アプリケーションのリストには次のものが含まれています。
- PowerPoint
- Excel
- Word
- Microsoft Teams
- Microsoft SharePoint
- Microsoft Visio ビューアー
- OneDrive
- OneNote
- Outlook

次の表では、推奨される設定について説明します。

|型|[プロパティ]|値|メモ|
|:---|:---------|:-----|:----|
|データ再配置|[Android でのバックアップを禁止する]|はい|iOS では、特に iTunes と iCloud が呼び出されます|
||[アプリで他のアプリへのデータ転送を許可する]|ポリシーで管理されているアプリ||
||このアプリで他のアプリからデータを受信できるようにする|ポリシーで管理されているアプリ||
||[名前を付けて保存] を禁止する|はい||
||会社のデータを保存できるストレージ サービスの選択|ビジネスでは、SharePoint の OneDrive||
||他のアプリとの間で切り取り、コピー、貼り付けを制限する|ポリシー管理対象のアプリケーションでの貼り付けで||
||Web コンテンツを管理対象ブラウザーで表示するように制限する|[いいえ]||
||[アプリ データの暗号化]|はい|iOS では、[デバイスがロックされている場合] オプションを選択します|
||デバイスが有効になっているときに、アプリケーションの暗号化を無効にします。|はい|二重の暗号化を回避するには、この設定を無効にします。|
||連絡先の同期を無効にする|[いいえ]||
||印刷を無効にします。|[いいえ]||
|アクセス|アクセスのために PIN を要求する|はい||
||タイプを選択します。|数値||
||単純な PIN を許可する|[いいえ]||
||PIN の長さ|6 ||
||PIN の代わりに指紋を要求する|はい||
||デバイスの暗証番号 (pin) が管理されている場合は、暗証番号 (pin) のアプリケーションを無効にします。|はい||
||アクセスのために企業の資格情報を必要とします。|いいえ||
||[(分数) 後に、アクセス要件を再確認する]|30||
||[スクリーン キャプチャと Android Assistant をブロックする]|[いいえ]|iOS では、このオプションは使用できません|
|サインインのセキュリティ要件|最大 PIN の試行|5 |Pin をリセットします。|
||[オフラインの猶予期間]|720|アクセスの禁止|
||アプリのデータがワイプされるまでのオフライン期間 (日数)|90|データを消去します。|
||Jailbroken とルート デバイス| |データを消去します。|

完了したら、必ず [作成] をクリックしてください。 上記の手順を繰り返し、選択されているプラットフォーム (ドロップダウン) を iOS に置き換えます。 これで 2 つのアプリ ポリシーが作成されます。作成されたポリシーにグループを割り当ててから、そのポリシーを展開してください。

ポリシーを編集し、ユーザーにこれらのポリシーを割り当て、[作成し、アプリケーションの保護ポリシーを割り当てる方法](https://docs.microsoft.com/intune/app-protection-policies)を参照してください。 

## <a name="require-approved-apps"></a>承認済みのアプリケーションを必要とします。
必要とするには、アプリケーションを承認します。

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。 正常にサインインすると、Azure ダッシュボードが開きます。

2. 左側のメニューから **[Azure Active Directory]** を選びます。

3. **[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。

4. **[新しいポリシー]** を選びます。

5. ポリシー名を入力し、ポリシーを適用する **[ユーザーとグループ]** を選びます。

6. **[クラウド アプリ]** を選びます。

7. **アプリケーションの選択**を選択して、**クラウドのアプリ**一覧から目的のアプリケーションを選択します。たとえば、Office 365 の Exchange のオンラインを選択します。**選択**し、[**完了**] をクリックします。

8. **[アクセス制御]** セクションから **[許可]** を選びます。

9. **クライアント アプリケーションの承認を必要とする**を選択して、**アクセスを許可する**を選択します。 複数のコントロールでは、**選択したコントロールを必要と**するを選択し、**選択**を選択します。 

10. [ **作成**] をクリックします。

## <a name="define-device-compliance-policies"></a>デバイスのコンプライアンス ・ ポリシーを定義します。

デバイスのコンプライアンス ・ ポリシーは、デバイス準拠としてマークするために従う必要がある要件を定義します。Intune デバイスから Azure ポータル内でのコンプライアンス ・ ポリシーを作成します。 

プラットフォームごとにポリシーを作成します。
- Android
- Android エンタープライズ
- iOS
- macOS
- Windows Phone 8.1
- およびそれ以降の Windows 8.1
- Windows 10 以降

デバイスのコンプライアンス ・ ポリシーを作成するに、管理者の資格情報を使用して、Microsoft Azure ポータルにログインしに移動**Intune > デバイス対応**です。**ポリシーの作成**] をクリックします。

次の設定は、Windows の 10 に適しています。

**デバイス状態: Windows の稼働状態の認証サービスの評価の規則**

|[プロパティ]|値|メモ|
|:---------|:-----|:----|
|BitLocker を必要とします。|必須||
|デバイスで有効にする、セキュリティで保護されたブートを必要とします。|必須||
|コードの整合性を必要とします。|必須||


**デバイスのプロパティ**

|型|[プロパティ]|値|メモ|
|:---|:---------|:-----|:----|
|オペレーティング システムのバージョン|すべて|未構成||

上記のすべてのポリシーを展開済みと見なすには、ユーザー グループを対象にする必要があります。 そのためには、(保存) ポリシーを作成するか、後でポリシー セクション (追加と同じレベル) で [展開の管理] を選択します。

**システム セキュリティ**

|型|[プロパティ]|値|メモ|
|:---|:---------|:-----|:----|
|Password|モバイル デバイスのロックを解除するパスワードを要求します。|必須||
||単純なパスワード|ブロック||
||パスワードの種類|デバイスの既定値||
||パスワードの最小文字数|6 ||
||パスワードが要求される前にアクティブでない最大の分|15 |Android バージョン 4.0 以降では、この設定はサポートされてまたは連盟ノックス ・ 4.0 およびそれ以上。IOS デバイスは、iOS 8.0 以降でサポートされます。|
||パスワードの有効期限 (日)|41||
||再利用を防ぐために以前のパスワードの数|5 ||
||デバイス (モバイルおよび Holographic)、アイドル状態から制御が戻るときにパスワードを必要とします。|必須|Windows 10 およびそれ以降を使用できます。|
|暗号化|デバイス上のデータ ・ ストレージの暗号化|必須||
|デバイスのセキュリティ|ファイアウォール|必須||
||ウイルス対策|必須||
||スパイウェア対策|必須|この設定には、Windows セキュリティ センターに登録されているスパイウェア対策ソリューションが必要です。|
|Defender|Windows Defender のウイルス対策|必須||
||Windows Defender マルウェア対策用の最小バージョン||10 の Windows デスクトップでのみサポートされています。マイクロソフトは、以下最新のバージョンから 5 の背後にあるバージョンをお勧めします。|
||Windows Defender のウイルス対策署名を最新の状態|必須||
||リアルタイム保護|必須|10 の Windows デスクトップでのみサポートされています。|

**Windows Defender ATP**

|型|[プロパティ]|値|メモ|
|:---|:---------|:-----|:----|
|Windows Defender の高度な脅威保護のルール|またはコンピューターのリスク ・ スコアの下にデバイスを必要とします。|中||





## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>準拠の Pc (ですが、準拠していないフォンやタブレット) を必要とします。
準拠の Pc を必要とするポリシーを追加する前に必ず Intune への管理用のデバイスを登録してください。Intune に確実に目的のユーザーの所有していることには、デバイスのデバイスを登録する前に、多要素認証を使用することをお勧めします。 

適合した Pc が必要です。

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。 正常にサインインすると、Azure ダッシュボードが開きます。

2. 左側のメニューから **[Azure Active Directory]** を選びます。

3. **[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。

4. **[新しいポリシー]** を選びます。

5. ポリシー名を入力し、ポリシーを適用する **[ユーザーとグループ]** を選びます。

6. **[クラウド アプリ]** を選びます。

7. **アプリケーションの選択**を選択して、**クラウドのアプリ**一覧から目的のアプリケーションを選択します。たとえば、Office 365 の Exchange のオンラインを選択します。**選択**し、[**完了**] をクリックします。

8. 準拠を必要とするには、Pc が、準拠していないフォンやタブレット、**条件**と**デバイスのプラットフォーム**を選択します。「プラットフォームのデバイスを選択します」を選択し**Windows**と**macOS**を選択します。

9. **[アクセス制御]** セクションから **[許可]** を選びます。

10. **準拠としてマークするデバイスを必要とする**を選択して、**アクセスを許可する**を選択します。 複数のコントロールには、**選択したすべてのコントロールを必要と**するを選択し、**選択**を選択します。 

11. [ **作成**] をクリックします。

準拠の Pc*と*モバイル デバイスを必要とする目的がある場合、プラットフォームを選択することはしません。これは強制すべてのデバイスに対応します。 




## <a name="require-compliant-pcs-and-mobile-devices"></a>準拠の Pc*と*モバイル デバイスを必要とします。

すべてのデバイスのコンプライアンスが必要です。

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。 正常にサインインすると、Azure ダッシュボードが開きます。

2. 左側のメニューから **[Azure Active Directory]** を選びます。

3. **[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。

4. **[新しいポリシー]** を選びます。

5. ポリシー名を入力し、ポリシーを適用する **[ユーザーとグループ]** を選びます。

6. **[クラウド アプリ]** を選びます。

7. **アプリケーションの選択**を選択して、**クラウドのアプリ**一覧から目的のアプリケーションを選択します。たとえば、Office 365 の Exchange のオンラインを選択します。**選択**し、[**完了**] をクリックします。

8. **[アクセス制御]** セクションから **[許可]** を選びます。

9. **準拠としてマークするデバイスを必要とする**を選択して、**アクセスを許可する**を選択します。複数のコントロールには、**選択したすべてのコントロールを必要と**するを選択し、**選択**を選択します。 

10. [ **作成**] をクリックします。

このポリシーを作成する場合、プラットフォームを選択することはしません。これは、デバイスの準拠を強制します。















<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a>次の手順

[電子メールをセキュリティで保護するためのポリシーの推奨事項について学びます](secure-email-recommended-policies.md)
