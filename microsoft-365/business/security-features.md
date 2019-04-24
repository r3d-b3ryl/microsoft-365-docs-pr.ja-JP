---
title: Microsoft 365 Business セキュリティ機能
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-security-compliance
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Microsoft 365 Business に付属しているセキュリティ機能について説明します。
ms.openlocfilehash: 24d4c4e79e7d8737beb82336796956774f127209
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286886"
---
# <a name="microsoft-365-business-security-features"></a>Microsoft 365 Business セキュリティ機能

Microsoft 365 Business では、pc、携帯電話、タブレットでデータを保護するための簡単なセキュリティ機能が提供されています。
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Microsoft 365 Business 管理センターのセキュリティ機能

管理センターでは、Microsoft 365 Business セキュリティ機能の多くを管理することができます。これにより、これらの機能を簡単にオンまたはオフにすることができます。 管理センターでは、次の操作を実行できます。
  
![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
- [Android または iOS デバイスのアプリケーション管理設定を設定](app-protection-settings-for-android-and-ios.md)します。 
    
    これらの設定には、設定期間後に非アクティブなデバイスからファイルを削除する、作業ファイルを暗号化する、ユーザーに PIN を設定することなどが含まれます。
    
- [Windows 10 デバイスのアプリケーション保護設定を設定](protection-settings-for-windows-10-devices.md)します。 
    
    これらの設定は、会社所有のデバイスまたは個人所有のデバイスの両方で会社のデータに適用できます。
    
- [Windows 10 デバイスのデバイス保護設定を設定](protection-settings-for-windows-10-pcs.md)します。 
    
    デバイスが紛失または盗難にあった場合にデータを保護するために[BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405)暗号化を有効にし、 [Windows Exploit Guard](https://go.microsoft.com/fwlink/p/?linkid=871404)がランサムウェアに対する高度な保護を提供できるようにします。 
    
- [デバイスから会社のデータを削除する](remove-company-data.md)
    
    デバイスが紛失、盗難、または従業員が退職した場合、会社のデータをリモートでワイプできます。
    
- [Windows 10 デバイスを出荷時の設定にリセット](reset-devices-to-factory-settings.md)します。 
    
    デバイス保護設定が適用されているすべての Windows 10 デバイスをリセットできます。
    
## <a name="additional-security-features"></a>その他のセキュリティ機能 

Microsoft 365 business の高度な機能を使用すると、サイバー脅威からビジネスを保護し、機密情報を保護することができます。
  
- **[Office 365 Advanced Threat Protection](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    Advanced Threat Protection (ATP) は、従業員または顧客の情報を侵害するように設計された高度なフィッシングおよびランサムウェア攻撃からビジネスを保護するのに役に立ちます。 以下の機能があります。
    
  - 高度な添付ファイルスキャンと AI による分析により、危険なメッセージを検出して破棄します。
    
  - 電子メールの web リンクを自動チェックして、それらがフィッシング詐欺スキームの一部であるかどうかを評価します。 これにより、安全でない web サイトへのアクセスが安全に保たれます。
    
- **[データ損失防止ポリシーの概要](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)**(DLP)。 
    
    DLP を設定して、クレジットカード番号、社会保障番号などの機密情報を自動的に検出し、会社外との偶発的な共有を防ぐことができます。
    
- **[Exchange Online Archiving](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online のアーカイブライセンスでは、継続的なデータバックアップを使用してメッセージを簡単にアーカイブできます。 削除済みアイテムを含むすべてのユーザーの電子メールを、後で検出または復元するときに必要に応じて保存します。 また、さまざまなアイテム保持ポリシーを使用して、訴訟ホールド、電子情報開示、またはコンプライアンス要件を満たすために電子メールデータを保持することができます。
    
- **[Azure Information Protection](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    情報保護は、「転送不可」や「コピーしない」などのコントロールを使用して、電子メールやドキュメント内の機密情報へのアクセスを制御するのに役に立ちます。 機密情報を "機密" として分類し、ビジネスの外部および内部で分類情報を共有する方法を指定することもできます。 エンタープライズレベルの暗号化は、情報の機密を保持するために電子メールやドキュメントに簡単に適用できます。 Microsoft 365 Business には、 [Azure Information Protection プラン 1](https://go.microsoft.com/fwlink/p/?linkid=871407)のすべての機能が含まれています。 Office アプリ用の Azure Information Protection クライアントアドインをインストールすることもできます。 詳細については、「 [Azure Information Protection クライアントの admininstrator ガイド](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide)」を参照してください。
    
- **[Azure portal の Intune のすべての機能](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Azure portal の Intune 管理センターにアクセスすることにより、Microsoft では提供されていない、Windows 用アドバンストデバイス管理と共に、MacOS デバイス、iPhone、Android デバイスの管理など、追加のセキュリティ機能を設定できます。365 Business 管理センター
    
次のセクションでは、これらの機能をセキュリティ&amp;コンプライアンスセンターおよび Intune 管理センターで管理する方法について説明します。 時間の経過とともに、簡略化された統制は Microsoft 365 Business 管理センターに追加されます。
  
## <a name="set-up-advanced-threat-protection-features"></a>高度な脅威保護機能をセットアップする

- **安全でない添付ファイルから保護する:** ATP は、仮想環境で電子メールの添付ファイルを開いて、結果の動作の分析を実行することで、悪意のあるコンテンツを特定します。 コンテンツを評価して、その意図 (通常または悪意) を判断し、ATP が安全でない添付ファイルの配信をブロックすることで、フィッシング詐欺やランサムウェアによる感染から保護します。 添付ファイル保護をアクティブにするには、「 [Office 365 ATP の安全な添付ファイルのポリシーを](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775)セットアップする」を参照してください。
    
- ユーザーが悪意のあるリンクをクリックしたときに環境を保護します。 ATP では、ユーザーがクリックしたときに電子メール内のリンクもチェックされます。 リンクが安全でない場合、ユーザーはサイトにアクセスしないように警告が出されるか、サイトがブロックされていることが通知されます。 これにより、フィッシングを防ぐことができます。 [office 365 atp safe links ポリシーを](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc)セットアップするか、 [office 365 atp safe links ポリシーを](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc)セットアップすることができます。
    
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

web 上の Outlook でメールを送信するときに以下の制限を適用する機能は、すべてのユーザーに対して自動的に有効になります。
  
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

1. [Microsoft ダウンロードセンター](https://www.microsoft.com/download/details.aspx?id=53018)から**azinfoprotection**をダウンロードします。
 
2. Word 文書を表示し、[**ホーム**] タブで [**保護**] オプションが有効になっていることを確認することで、インストールが正常に行われたことを確認できます。 <br/>![Word 文書内の [保護] タブのドロップダウン](media/Word_Protect.png)

詳細については、「[クライアントをインストールする](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)」を参照してください。

## <a name="go-to-intune-admin-center"></a>Intune 管理センターに移動します。

1. [Azure portal](https://portal.azure.com/)にサインインします。

2. [**すべてのサービス**] を選択し、**検索ボックス**に「 *Intune* 」と入力します。

3. 結果が表示されたら、[ **Microsoft Intune** ] の横にある [開始] をクリックして、お気に入りにし、後で見つけやすいようにします。
 
Intune を使用して、組織のデバイスの登録と管理を行うことができます。 詳細については、「 [Windows デバイスの登録方法](https://docs.microsoft.com/intune/enrollment-method-capabs)」および「 [Intune によって管理されるデバイスの登録オプション](https://docs.microsoft.com/intune/enrollment-options)」を参照してください。
    
## <a name="faq"></a>FAQ

 ### <a name="are-these-security-features-available-in-all-markets"></a>これらのセキュリティ機能はすべての市場で利用できますか?
  
はい。これらの機能は、Microsoft 365 Business が販売されているすべての市場で利用できます。
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>セキュリティ&amp;コンプライアンスセンターを見つけるには、どうすればよいですか。
  
1. 管理者の資格情報を使用して、 [Microsoft 365 Business にサインイン](https://portal.microsoft.com/)します。 
    
2. 左側のナビゲーションで、[**管理センター** ] を見つけて展開します。 
    
    ![Microsoft 365 管理センターの左側のナビゲーションで、[管理センター] を選択します。](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. [**セキュリティ&amp;コンプライアンス**] を選択し&amp;て、セキュリティ/コンプライアンスセンターに移動します。