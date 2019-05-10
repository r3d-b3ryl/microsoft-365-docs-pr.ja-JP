---
title: Microsoft 365 Business ユーザーの高度なセキュリティポリシーをセットアップする
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Office 365 Advanced Threat Protection を設定し、機密データを保護します。
ms.openlocfilehash: 4728e11a16fdf8a461f5687632df75699923f846
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "33663646"
---
# <a name="set-up-advanced-security-policies"></a>高度なセキュリティポリシーをセットアップする

[管理センター](security-features.md#microsoft-365-business-admin-center-security-features)で設定できるポリシーに加えて、 [Office 365 Advanced Threat protection](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653) (ATP) を設定することによって、サイバー脅威に対する保護を追加することができます。 また、機密情報を保護するには、[データ損失防止](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)(DLP)、Azure information PROTECTION (AIP)、 [Exchange Online アーカイブ](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)をセットアップして、 [Intune ポータル](#go-to-intune-admin-center)でデバイスを管理することもできます。

業務を保護するための最も重要な方法の概要については、「 [Microsoft 365 のセキュリティを保護するための10の方法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)」を参照してください。これには、MFA を使用して、2番目のサインインフォームを作成することも含まれます。

簡単に操作する方法については[、「ビジネストレーニングのビデオを保護](https://support.office.com/article/e12187b8-216a-4490-9e3b-df34a06fb787)する」を参照してください。

## <a name="increase-email-malware-protection"></a>メールマルウェア対策の向上

マルウェアとは、コンピューターまたはネットワークに損害を与える可能性があるソフトウェアで、個人情報や顧客情報などのデータをユーザーから盗むことがあります。 Microsoft 365 Business には、マルウェアに対する保護のベースラインレベルが含まれていますが、追加の設定を設定することで、この保護を強化することができます。 手順については、「[マルウェア検出トレーニングビデオを有効にする](https://support.office.com/article/02b5783a-eea0-42e8-8856-62440718c3f0)」を参照してください。

## <a name="set-up-advanced-threat-protection-features"></a>高度な脅威保護機能をセットアップする

- **安全でない添付ファイルから保護する:** ATP は、仮想環境で電子メールの添付ファイルを開いて、結果の動作の分析を実行することで、悪意のあるコンテンツを特定します。 コンテンツを評価して、その意図 (通常または悪意) を判断し、ATP が安全でない添付ファイルの配信をブロックすることで、フィッシング詐欺やランサムウェアによる感染から保護します。 添付ファイルの保護を有効にするには、「 [Office 365 ATP の安全な添付ファイルをセットアップ](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775)する」を参照してください。また、悪意のある[ファイルからの保護](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)についての短いトレーニングビデオ
    
- **ユーザーが悪意のあるリンクをクリックしたときに環境を保護します。** また、ATP は、ユーザーがクリックしたときに電子メール内のリンクを調べます。 リンクが安全でない場合、ユーザーはサイトにアクセスしないように警告が出されるか、サイトがブロックされていることが通知されます。 これにより、フィッシングを防ぐことができます。 これを有効にするには、「 [Office 365 の ATP 安全](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies)な[](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)リンクの設定」を参照してください。

- **お客様の環境をフィッシングから保護します。** ATP のフィッシング対策は、一連の機械学習モデルを受信メッセージに適用して、他のユーザーが既知の情報を抽出して情報を抽出しようとしているフィッシング攻撃からの保護を提供します。情報. これを有効にするには、「 [ATP のフィッシング対策の](https://docs.microsoft.com/office365/securitycompliance/set-up-anti-phishing-policies)ヘルプドキュメントを設定する」および「[フィッシングからの保護に](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)ついて」の短いトレーニングビデオを参照してください。

## <a name="set-up-dlp-features"></a>DLP 機能を設定する

個人を特定できる情報 (PII) を保護するポリシーを設定する方法の例については、「[テンプレートからの DLP ポリシーの作成](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)」を参照してください。 
  
DLP には、さまざまなロケールに対して、多くの使用可能なポリシーテンプレートが用意されています。 たとえば、オーストラリアの財務データ、カナダの個人情報法、米国金融データなど。完全なリストについては[、DLP ポリシーテンプレートに含まれるもの](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)を参照してください。 これらのテンプレートはすべて、PII テンプレートの例と同様に有効にすることができます。 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Exchange Online アーカイブを使用したメールの保存期間の設定

 **Exchange Online アーカイブ**ライセンス機能を使用すると、電子情報開示の目的で電子メールコンテンツを保持することで、コンプライアンスおよび規制基準を維持することができます。 また、訴訟が発生した場合のリスクを軽減し、セキュリティ違反が発生した後や、削除済みアイテムを復元する必要がある場合にも、データを回復することができます。 これらの機能を有効にするには、訴訟ホールドを使用して、すべてのユーザーのコンテンツを保持するか、アイテム保持ポリシーを使用してカスタマイズを強化できます。 
  
**訴訟ホールド:** ユーザーのメールボックスを訴訟ホールドの対象にすることで、削除されたアイテムを含むすべてのメールボックスのコンテンツを保持できます。 
    
メールボックスを訴訟ホールドの対象にするには、管理センターで次のようにします。
    
1. 左側のナビゲーションで、[**ユーザー** \> ] [**アクティブなユーザー**] に移動します。
    
2. 訴訟ホールドの対象とするメールボックスを持つユーザーを選択し、ユーザーウィンドウで [**メールの設定**] を展開し、[**その他の設定**] の横にある [ **Exchange プロパティの編集**] を選択します。
    
3. ユーザーのメールボックスページで、左側のナビゲーションにある [* * メールボックスの機能] を選択し、[**訴訟ホールド**] の下の [**有効にする**] リンクを選択します。
    
4. [**訴訟**ホールド] ダイアログボックスで、[**訴訟ホールド期間**] フィールドに訴訟ホールド期間を指定することができます。無限に保持する場合は、フィールドを空のままにします。 また、メモを追加して、メールボックスの所有者を web サイトに誘導することもできます。 \>これにより、訴訟ホールドの**保存**について詳細に説明する必要があります。
    
**保持:** 保持期間の終了時に、特定の時間だけ保持したり、コンテンツを完全に削除したりするために、カスタマイズされた保持ポリシーを有効にすることができます。 詳細については、「[アイテム保持ポリシーの概要](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)」を参照してください。
## <a name="set-up-azure-information-protection-features"></a>Azure Information Protection 機能をセットアップする

Azure Information Protection (AIP) は、組織がラベルを適用することで、ドキュメントや電子メールを分類し、必要に応じて保護できる、クラウドベースのソリューションです。 ラベルは、ルールと条件を定義する管理者、ユーザーによって手動で、またはユーザーが推奨事項を与える組み合わせによって自動的に適用されます。

Web 上の Outlook でメールを送信するときに以下の制限を適用する機能は、すべてのユーザーに対して自動的に有効になります。
  
- **転送不可**: 受信者はメッセージを読み取ることはできますが、コンテンツを転送、印刷、またはコピーすることはできません
    
- **Encrypt**: メッセージ全体が暗号化されます。 暗号化されたコンテンツにアクセスする前に、id を確認するために、受信者は特別な手順を実行する必要があります。
    
- **社外秘**: 組織内の従業員に電子メールのコンテンツと添付ファイルへの完全なアクセス許可は付与されますが、組織外のユーザーに対しては含まれません。 データ所有者は、任意の時点でコンテンツを追跡して取り消すことができます。
    
- **高機密**: この制限は機密性の高いデータに適用できるため、従業員はデータの表示、編集、および返信を行うことはできませんが、転送、印刷、またはコピーはできません。 データ所有者は、任意の時点でコンテンツを追跡して取り消すことができます。

### <a name="make-sure-azure-information-protection-is-activated"></a>Azure Information Protection がアクティブ化されていることを確認する

AIP がアクティブ化されていることを確認するには

1. [Azure portal](https://portal.azure.com/)にサインインします。

2. [**すべてのサービス**] を選択し、[**検索] ボックス**に「 *Azure Information Protection* 」と入力します。

3. 結果が表示されたら、 **Azure Information Protection**の横にある [開始] をクリックして、お気に入りにし、後で見つけやすいようにします。

4. [ **Azure Information protection** \> **protection activation** ] を選択し、状態が [アクティブ] に設定されていることを確認します。 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a>Azure Information Protection ポリシーと既定のラベルを表示する 

既存のラベルを表示および変更するには、次のようにします。

1. [Azure Information Protection] ダッシュボードで、[**分類** \> **ラベル**] を選択します。 <br/>![Azure Information Protection の標準ラベル。](media/AIPLabels.png)

2. 任意のラベルを選択してオプションを表示したり、表示名や色などを変更したりできます。
 
3. 独自のラベルを作成する場合は、「[変更して新しいラベルを作成](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2)する」を参照してください。 

### <a name="install-the-azure-information-protection-client-manually"></a>Azure Information Protection クライアントを手動でインストールする

AIP クライアントを手動でインストールするには、次のようにします。

1. [Microsoft ダウンロードセンター](https://www.microsoft.com/download/details.aspx?id=53018)から**Azinfoprotection**をダウンロードします。
 
2. Word 文書を表示し、[**ホーム**] タブで [**保護**] オプションが有効になっていることを確認することで、インストールが正常に行われたことを確認できます。 <br/>![Word 文書内の [保護] タブのドロップダウン](media/Word_Protect.png)

詳細については、「[クライアントをインストールする](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)」を参照してください。

## <a name="go-to-intune-admin-center"></a>Intune 管理センターに移動します。

1. [Azure portal](https://portal.azure.com/)にサインインします。

2. [**すべてのサービス**] を選択し、**検索ボックス**に「 *Intune* 」と入力します。

3. 結果が表示されたら、[ **Microsoft Intune** ] の横にある [開始] をクリックして、お気に入りにし、後で見つけやすいようにします。

管理センターに加えて、Intune を使用して組織のデバイスを登録および管理することができます。 詳細については、「 [Windows デバイスの登録方法](https://docs.microsoft.com/intune/enrollment-method-capabs)」および「 [Intune によって管理されるデバイスの登録オプション](https://docs.microsoft.com/intune/enrollment-options)」を参照してください。

## <a name="microsoft-secure-score"></a>Microsoft セキュア スコア

