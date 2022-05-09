---
title: IT 管理者向けのOfficeドキュメントでアクティブなコンテンツを管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: tutorial
ms.localizationpriority: medium
ms.prod: m365-security
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ROBOTS: NOINDEX,NOFOLOW
description: 管理者は、Officeドキュメント内のアクティブなコンテンツをブロックするポリシーを作成する方法を学習できます
ms.openlocfilehash: 7a24c56bdd388f2dc9a8f408b52b2de1c6805a0a
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65100943"
---
# <a name="manage-active-content-in-office-documents"></a>Office ドキュメントでアクティブなコンテンツを管理する

> [!NOTE]
> この記事で説明する機能はプレビュー版であり、すべてのユーザーが利用できるわけではなく、変更される可能性があります。

Officeドキュメントには、_アクティブなコンテンツ_ が含まれている場合に自動的に更新、更新、または実行できます。 アクティブなコンテンツの例として、マクロ、ActiveX コントロール、Office アドインがあります。アクティブ コンテンツは、ユーザーに強力で便利な機能を提供できますが、攻撃者はアクティブ なコンテンツを使用してマルウェアを配信することもできます。

管理者は、アクティブ なコンテンツの使用を特定のユーザー セットに制限する組織ポリシー (グループ ポリシーまたはクラウド ポリシー) を作成したり、アクティブなコンテンツを完全に無効にしたりできます。 ユーザーは、ファイル **オプション** セキュリティ センターのOffice アプリで、Office セキュリティ **センター** で独自のセキュリティとプライバシーの設定 **を** \> \>構成できます。

以前は、ユーザーがドキュメントを信頼できるドキュメントとして識別した場合、管理者がOfficeドキュメント内のアクティブなコンテンツをブロックするようにポリシーを構成した場合でも、アクティブなコンテンツを実行できます。 これで、管理者によって設定されたポリシーが、信頼できるドキュメントのユーザー識別よりも優先されるようになりました。 この動作の変更により、ユーザーに問題が発生する可能性があります。

更新されたトラスト センター ロジックについては、次の図で説明します。

:::image type="content" source="../media/office-trust-center-flow.png" alt-text="Microsoft 365 Defender ポータルのトラスト センター ロジックを説明するフローチャート" lightbox="../media/office-trust-center-flow.png":::

1. ユーザーが、アクティブなコンテンツを含むOfficeドキュメントを開きます。

2. ドキュメントが信頼できる場所にある場合は、作業中のコンテンツが有効になっている状態でドキュメントが開きます。 ドキュメントが信頼できる場所からでない場合、評価は続行されます。

3. 更新された動作が有効になります。
   - 以前は、次に評価される設定は、ユーザーがこのドキュメントを信頼できるドキュメントとして識別した場合でした。 その場合、作業中のコンテンツが有効になっている状態でドキュメントが開きます。
   - これで、ユーザーがドキュメントを信頼済みドキュメントとして識別したかどうかは、ここでは考慮されません (手順 8 に進みます)。

     動作の基本的な変更については、クラウド ポリシー (手順 4)、グループ ポリシー (手順 6)、およびローカル設定 (手順 7) が確認 _されてから_ 、信頼されたドキュメントのユーザー指定が考慮されます。 これらの手順のいずれかがアクティブなコンテンツへのアクセスをブロック **し、** どの手順もユーザーのオーバーライドを許可しない場合、ドキュメントを信頼されたドキュメントとしてユーザー識別することは無関係です。

4. クラウド ポリシーは、この種類のアクティブなコンテンツが許可されているかブロックされているかを確認するためにチェックされます。 アクティブなコンテンツがブロックされていない場合、評価は手順 6 に進みます。

   アクティブなコンテンツがポリシーによってブロックされている場合は、手順 5 でエクスペリエンスについて説明します。

5. ドキュメントの開きは、信頼バーの通知でブロックされます。 次に何が起こるかは、ポリシーのユーザー オーバーライド設定 (a) によって制御されます。 **ユーザーオーバーライドは許可されません**。ユーザーはドキュメントを開けず、評価が停止します。
   b. **許可されているユーザーオーバーライド**: ユーザーは、信頼バーのリンクをクリックして、作業中のコンテンツが有効になっているドキュメントを開くことができます。

6. グループ ポリシーは、この種類のアクティブなコンテンツが許可されているかブロックされているかを確認するためにチェックされます。 アクティブなコンテンツがブロックされていない場合、評価は手順 7 に進みます。

   アクティブなコンテンツがポリシーによってブロックされている場合は、手順 5 でエクスペリエンスについて説明します。

7. ローカル設定は、この種類のアクティブなコンテンツが許可されているかブロックされているかを確認するためにチェックされます。 アクティブなコンテンツがブロックされている場合、ドキュメントの開きは信頼バーの通知でブロックされます。 アクティブなコンテンツがブロックされていない場合、評価は続行されます。

8. ユーザーが以前にドキュメントを信頼できるドキュメントとして識別した場合、作業中のコンテンツが有効になっている状態でドキュメントが開きます。 そうでない場合、ドキュメントの開きはブロックされます。

## <a name="what-is-a-trusted-document"></a>信頼できるドキュメントとは何ですか?

信頼できるドキュメントはOfficeドキュメントであり、ドキュメント内のマクロ、ActiveX コントロール、その他の種類のアクティブなコンテンツのセキュリティ プロンプトなしで開きます。 保護されたビューまたは Application Guard は、ドキュメントを開くために使用されません。 ユーザーが信頼できるドキュメントを開き、アクティブなすべてのコンテンツが有効になっている場合。 ドキュメントに新しいアクティブコンテンツが含まれている場合や、既存のアクティブなコンテンツに対する更新プログラムが含まれている場合でも、ユーザーは次回ドキュメントを開いたときにセキュリティプロンプトを受け取りません。

この動作のため、ユーザーはドキュメント ソースを信頼している場合にのみ、ドキュメントを明確に信頼する必要があります。

管理者がポリシーを使用してアクティブなコンテンツをブロックする場合、またはユーザーがアクティブなコンテンツをブロックするセキュリティ センター設定を設定した場合、アクティブなコンテンツはブロックされたままになります。

詳細については、次の記事を参照してください。

- [信頼できるドキュメント](https://support.microsoft.com/topic/trusted-documents-cf872bd8-47ec-4c02-baa5-1fdba1a11b53)
- [信頼できる場所を追加、削除、または変更する](https://support.microsoft.com/topic/add-remove-or-change-a-trusted-location-7ee1cdc2-483e-4cbb-bcb3-4e7c67147fb4)
- [ファイル内のアクティブなコンテンツ タイプ](https://support.microsoft.com/topic/active-content-types-in-your-files-b7ff2e8a-4055-47d4-8c7d-541e19f62bea)

## <a name="configure-trusted-document-settings-in-office-policies"></a>Office ポリシーで信頼できるドキュメント設定を構成する

管理者は、組織内でOfficeを構成するさまざまな方法があります。 例:

- **Office クラウド ポリシー サービス**: Azure AD アカウントを使用して、Office アプリ内のファイルにアクセスする任意のデバイス上のユーザーに適用されるユーザー ベースのポリシーを設定します。 [Office Cloud Policy Service でOfficeクラウド ポリシー構成を作成](/DeployOffice/overview-office-cloud-policy-service)する手順[を参照](https://config.office.com/officeSettings/officePolicies)してください。
- **IntuneのOffice ポリシー**: Intune 設定 カタログまたは管理用テンプレートを使用して、WINDOWS 10 PC に HKCU ポリシーを展開します。デバイス **構成プロファイル** の [下の MEM 管理センター](https://endpoint.microsoft.com/#blade/Microsoft_Intune_DeviceSettings/DevicesMenu/configurationProfiles)**で**\>。
  - ***管理用テンプレート***: Windows 10 テンプレートを使用して [管理用テンプレート](/mem/intune/configuration/administrative-templates-windows)を構成する手順を参照してください。
  - ***設定 カタログ (プレビュー)***: [設定 カタログ (プレビュー)](/mem/intune/configuration/settings-catalog) を使用する手順を参照してください。
- **グループ ポリシー**: オンプレミスの Active Directory を使用して、ユーザーとコンピューターにグループ ポリシー オブジェクト (GPO) を展開します。 この設定の GPO を作成するには、最新の[管理用テンプレート ファイル (ADMX/ADML) と Office カスタマイズ ツール (Microsoft 365 Apps for enterprise、Office 2019、Office 2016 用)](https://www.microsoft.com/download/details.aspx?id=49030) をダウンロードします。

## <a name="known-issues"></a>既知の問題

- ポリシー **VBA マクロ通知** (Access、PowerPoint、Visio、Word) または **マクロ通知** (Excel) が値 **[デジタル署名されたマクロを除くすべて無効にする]** に設定されている場合、期待される信頼バーは表示されず、設定が想定どおりに機能していても、バックステージの **セキュリティ情報** にブロックされたマクロの詳細が一覧表示されません。 Office チームはこの問題の解決に取り組んでいます。

## <a name="admin-options-for-restricting-active-content"></a>アクティブなコンテンツを制限するための管理者オプション

内部で作成されたコンテンツと、ユーザーがインターネットからダウンロードするコンテンツの信頼レベルには大きな違いがあります。 内部ドキュメントでアクティブなコンテンツを許可し、インターネットからのドキュメントでアクティブなコンテンツをグローバルに許可しないことを検討してください。

ユーザーが特定の種類のアクティブなコンテンツを必要としない場合、最も安全な方法は、ポリシーを使用してそのアクティブなコンテンツへのユーザー アクセスを無効にし、必要に応じて例外を許可することです。

次のポリシーを使用できます。

- **信頼できる場所**: 使用可能なグループの例外をオフにします。
- **信頼済みドキュメント**: 使用可能なグループの例外をオフにします。
- **すべてのアクティブなコンテンツを無効にする**: 個人の例外。

次のセクションの表では、アクティブなコンテンツを制御する設定について説明します。 これらのポリシーは、ユーザーに適用されると、信頼できるドキュメントに適用され、以前のエンド ユーザー エクスペリエンスは同じでない可能性があります。 テーブルには、推奨されるセキュリティ ベースライン設定も含まれており、オーバーライドを求めるユーザー プロンプトが使用可能な他の設定を特定します (ユーザーがアクティブなコンテンツを有効にすることを許可します)。

### <a name="hkey_current_user-settings"></a>HKEY_CURRENT_USER設定

<p>

****
|カテゴリ|アプリ|ポリシー名|セキュリティ ベースライン<br>設定 (推奨)|ユーザー プロンプトを使用した設定<br>使用可能なオーバーライドを指定しますか?|
|---|---|---|---|---|
|ActiveX|事業所|ActiveX コントロールの初期化|**6**|次の値の **場合ははい**。 <ul><li>**3**</li><li>**4**</li><li>**5**</li><li>**6**</li></ul>|
|ActiveX|事業所|アクティブな X One Off フォームを許可する|**[Outlook のコントロールのみ読み込む]**|いいえ|
|ActiveX|事業所|[ActiveX オブジェクトをチェックする]|セキュリティ ベースライン設定ではありません。|いいえ|
|ActiveX|事業所|すべての ActiveX を無効にする|セキュリティ ベースライン設定ではありません。|次の値の **場合ははい**。 <ul><li>**Disabled**</li><li>**未構成**</li></ul>|
|ActiveX|事業所|Forms3 でコントロールを読み込む|**1**|次の値の **場合ははい**。 <ul><li>**2**</li><li>**3**</li></ul>|
|アドイン&機能拡張|Excel <p> PowerPoint <p> Project <p> Publisher <p> Visio <p> Word|署名されていないアプリケーション アドインの信頼バー通知を無効にしてブロックする|**Enabled (有効)**|**値が [無効]** **の場合は [はい**] です。|
|アドイン&機能拡張|Excel <p> PowerPoint <p> Project <p> Publisher <p> Visio <p> Word|アプリケーション アドインには信頼できる発行元による署名が必要|**Enabled (有効)**|いいえ|
|アドイン&機能拡張|Excel|AutoRepublish 警告アラートを表示しない|**Disabled**|いいえ|
|アドイン&機能拡張|Excel|WEBSERVICE 関数通知設定|**通知ですべて無効にする**|次の値の **場合ははい**。 <ul><li>**通知ですべて無効にする**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|アドイン&機能拡張|事業所|Office クライアントが発行されたリンクのSharePoint サーバーをポーリングできないようにする|**Disabled**|いいえ|
|アドイン&機能拡張|事業所|ドキュメントおよびテンプレートによる UI の拡張を無効にする|Word で許可しない = True <p> Projectで許可しない = False <p> Excelで許可しない = True <p> Visio= False で許可しない <p> PowerPointで許可しない = True <p> アクセスで許可しない = True <p> Outlookで許可しない = True <p> Publisherで許可しない = True <p> InfoPath で許可しない = True|いいえ|
|アドイン&機能拡張|Outlook|[アドレス帳にアクセスするときの Outlook オブジェクト モデルに関する確認について構成する]|**自動的に拒否する**|次の値の **場合ははい**。 <ul><li>**ユーザーにプロンプトを表示する**</li><li>**コンピューターのセキュリティに基づいてユーザーにプロンプトを表示する**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|アドイン&機能拡張|Outlook|UserProperty オブジェクトの Formula プロパティにアクセスするときに、オブジェクト モデル プロンプトOutlook構成する|**自動的に拒否する**|次の値の **場合ははい**。 <ul><li>**ユーザーにプロンプトを表示する**</li><li>**コンピューターのセキュリティに基づいてユーザーにプロンプトを表示する**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|アドイン&機能拡張|Outlook|[[名前を付けて保存] を実行するときの Outlook オブジェクト モデルに関する確認について構成する]|**自動的に拒否する**|次の値の **場合ははい**。 <ul><li>**ユーザーにプロンプトを表示する**</li><li>**コンピューターのセキュリティに基づいてユーザーにプロンプトを表示する**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|アドイン&機能拡張|Outlook|[アドレス情報を読み込むときの Outlook オブジェクト モデルに関する確認について構成する]|**自動的に拒否する**|次の値の **場合ははい**。 <ul><li>**ユーザーにプロンプトを表示する**</li><li>**コンピューターのセキュリティに基づいてユーザーにプロンプトを表示する**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|アドイン&機能拡張|Outlook|[会議出席依頼および仕事の依頼に返信するときの Outlook オブジェクト モデルに関する確認について構成する]|**自動的に拒否する**|次の値の **場合ははい**。 <ul><li>**ユーザーにプロンプトを表示する**</li><li>**コンピューターのセキュリティに基づいてユーザーにプロンプトを表示する**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|アドイン&機能拡張|Outlook|[メール送信時の Outlook オブジェクト モデルに関する確認について構成する]|**自動的に拒否する**|次の値の **場合ははい**。 <ul><li>**ユーザーにプロンプトを表示する**</li><li>**コンピューターのセキュリティに基づいてユーザーにプロンプトを表示する**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|アドイン&機能拡張|Outlook|オブジェクト モデルのカスタム アクション実行プロンプトOutlook設定する|**自動的に拒否する**|次の値の **場合ははい**。 <ul><li>**ユーザーにプロンプトを表示する**</li><li>**コンピューターのセキュリティに基づいてユーザーにプロンプトを表示する**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|アドイン&機能拡張|PowerPoint|プログラムの実行|**disable (プログラムを実行しない)**|値が [有効] の **場合は [はい****] (実行する前にユーザーにプロンプトを表示)**|
|アドイン&機能拡張|Word <p> Excel|Smart Document によるマニフェストの使用を無効にする|**Enabled (有効)**|いいえ|
|DDE|Excel|Excelで動的データ Exchange (DDE) サーバーの起動を許可しない|**Enabled (有効)**|[**未構成**] の値は **[はい] です**。|
|DDE|Excel|Excelで動的データ Exchange (DDE) サーバー参照を許可しない|**Enabled (有効)**|次の値の **場合ははい**。 <ul><li>**Disabled**</li><li>**未構成**</li></ul>|
|DDE|Word|動的データ Exchange|**Disabled**|いいえ|
|Jscript & VBScript|Outlook|[1 回限りの Outlook フォームでのスクリプトの使用を許可する]|**Disabled**|いいえ|
|Jscript & VBScript|Outlook|パブリック フォルダー Outlookオブジェクト モデル スクリプトの実行を許可しない|**Enabled (有効)**|いいえ|
|Jscript & VBScript|Outlook|共有フォルダー Outlookオブジェクト モデル スクリプトの実行を許可しない|**Enabled (有効)**|いいえ|
|マクロ|Excel|マクロ通知|**デジタル署名されたマクロを除くすべてのマクロを無効にする**|次の値の **場合ははい**。 <ul><li>**Disabled**</li><li>**未構成**</li></ul>|
|マクロ|Access <p> PowerPoint <p> Project <p> Publisher <p> Visio <p> Word|VBA マクロ通知設定|**デジタル署名されたマクロを除くすべてのマクロを無効にする** <p> and <p> **信頼された発行元がマクロに署名する必要がある**|次の値の **場合ははい**。 <ul><li>**Disabled**</li><li>**未構成**</li></ul>|
|マクロ|Access <p> Excel <p> PowerPoint <p> Visio <p> Word|インターネットからのOffice ファイルでのマクロの実行をブロックする|**Enabled (有効)**|次の値の **場合ははい**。 <ul><li>**Disabled**</li><li>**未構成**</li></ul>|
|マクロ|Excel|Excel Open XML ブックで暗号化されたマクロをスキャンする|**暗号化されたマクロをスキャンする (既定)**|いいえ|
|マクロ|事業所|VBA が信頼されていないイントラネットの場所からのパスで typelib 参照を読み込めるようにする|**Disabled**|いいえ|
|マクロ|事業所|Automation セキュリティ|**[アプリケーションのマクロのセキュリティ レベルを適用する]**|いいえ|
|マクロ|事業所|ローカル コンピューター上の安全でない場所を参照する可能性がある VBA ライブラリ参照の他のセキュリティ チェックを無効にする|**Disabled**|いいえ|
|マクロ|事業所|マクロ ランタイム スキャン スコープ|**すべてのドキュメントに対して有効にする**|いいえ|
|マクロ|事業所|V3 シグネチャを使用する VBA マクロのみを信頼する|セキュリティ ベースライン設定ではありません。|いいえ|
|マクロ|Outlook|Outlook セキュリティ モード|**Outlook セキュリティ グループ ポリシーを使用する**|すべてのOutlook GPO 設定を有効にするために必要です。 <p> 依存関係として言及されています (このポリシーは、アクティブなコンテンツ自体をブロックしません)。|
|マクロ|Outlook|マクロのセキュリティ設定|**署名済みの警告、署名なしを無効にする**|次の値の **場合ははい**。 <ul><li>**常に警告する**</li><li>**署名済みの警告、署名なしを無効にする**</li><li>**Disabled**</li><li>**未構成**</li></ul>|
|マクロ|PowerPoint|PowerPoint Open XML プレゼンテーションで暗号化されたマクロをスキャンする|**暗号化されたマクロをスキャンする (既定)**|いいえ|
|マクロ|Publisher|Publisher Automation セキュリティ レベル|**選択 (確認)**|いいえ|
|マクロ|Word|Word Open XML ドキュメントで暗号化されたマクロをスキャンする|**暗号化されたマクロをスキャンする (既定)**|いいえ|
|

### <a name="hkey_local_machine-settings"></a>HKEY_LOCAL_MACHINE設定

<p>

****
|カテゴリ|アプリ|ポリシー名|セキュリティ ベースライン<br>設定 (推奨)|ユーザー プロンプトを使用した設定<br>使用可能なオーバーライドを指定しますか?|
|---|---|---|---|---|
|ActiveX|事業所|[ActiveX のインストールを制限する] |excel.exe = True <p> exprwd.exe = True <p> groove.exe = True <p> msaccess.exe = True <p> mse7.exe = True <p> mspub.exe = True <p> onent.exe = True <p> outlook.exe = True <p> powerpnt.exe = True <p> pptview.exe = True <p> spDesign.exe = True <p> visio.exe = True <p> winproj.exe = True <p> winword.exe = True|いいえ|
|アドイン&機能拡張|事業所|[アドオンの管理] |excel.exe = True <p> exprwd.exe = True <p> groove.exe = True <p> msaccess.exe = True <p> mse7.exe = True <p> mspub.exe = True <p> onent.exe = True <p> outlook.exe = True <p> powerpnt.exe = True <p> pptview.exe = True <p> spDesign.exe = True <p> visio.exe = True <p> winproj.exe = True <p> winword.exe = True|いいえ|
|アドイン&機能拡張|事業所|Office ドキュメントで Flash のアクティブ化をブロックする|com killbits の一覧については、Microsoft Security Guide ADMX/ADML ファイルを参照して、Microsoft 365 アプリで Flash のすべてのアクティブ化をブロックします。 エンタープライズ セキュリティ ベースライン用の ADMX/ADML ファイルは、[セキュリティ コンプライアンス Toolkit](https://www.microsoft.com/download/details.aspx?id=55319)で使用できます。|いいえ|
|Jscript & VBScript|事業所|Officeのレガシ JScript実行を制限する|**有効:** <p> アクセス: 69632 <p> Excel: 69632 <p> OneNote: 69632 <p> Outlook: 69632 <p> PowerPoint: 69632 <p> Project: 69632 <p> Publisher: 69632 <p> Visio: 69632 <p> Word: 69632|いいえ|
|Jscript & VBScript|事業所|[スクリプト化されたウィンドウのセキュリティ制限] |excel.exe = True <p> exprwd.exe = True <p> groove.exe = True <p> msaccess.exe = True <p> mse7.exe = True <p> mspub.exe = True <p> onent.exe = True <p> outlook.exe = True <p> powerpnt.exe = True <p> pptview.exe = True <p> spDesign.exe = True <p> visio.exe = True <p> winproj.exe = True <p> winword.exe = True|いいえ|
|
