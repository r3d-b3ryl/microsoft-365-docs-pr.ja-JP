---
title: Microsoft 365 Business の脅威保護を強化する
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668395"
---
# <a name="set-up-compliance-features"></a>コンプライアンス機能を設定する

Microsoft 365 Business には、データとデバイスを保護するための機能が用意されており、お客様の機密情報を安全に保つために役立ちます。

## <a name="set-up-dlp-features"></a>DLP 機能を設定する

個人を特定できる情報 (PII) を保護するポリシーを設定する方法の例については、「[テンプレートからの DLP ポリシーの作成](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)」を参照してください。 
  
DLP には、さまざまなロケールに対して、多くの使用可能なポリシーテンプレートが用意されています。 たとえば、オーストラリアの財務データ、カナダの個人情報法、米国金融データなど。完全なリストについては[、DLP ポリシーテンプレートに含まれるもの](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)を参照してください。 これらのテンプレートはすべて、PII テンプレートの例と同様に有効にすることができます。 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Exchange Online アーカイブを使用したメールの保存期間の設定

 **Exchange Online のアーカイブ**ライセンス機能は、電子情報開示用の電子メールコンテンツを保持することで、コンプライアンスおよび規制基準を維持するのに役立ちます。 また、訴訟が発生した場合のリスクを軽減し、セキュリティ違反の後で、または削除済みアイテムを復元する必要がある場合にも、データを回復することができます。 訴訟ホールドを使用して、ユーザーのすべてのコンテンツを保持するか、保持ポリシーを使用して、保持する内容をカスタマイズできます。
  
**訴訟ホールド:** ユーザーのメールボックスを訴訟ホールドの対象にすることで、削除されたアイテムを含むすべてのメールボックスのコンテンツを保持できます。 
    
メールボックスを訴訟ホールドの対象にするには、管理センターで次のようにします。
    
1. 左側のナビゲーションで、[**ユーザー** \> ] [**アクティブなユーザー**] に移動します。
    
2. 訴訟ホールドの対象とするメールボックスを持つユーザーを選択し、ユーザーウィンドウで [**メールの設定**] を展開し、[**その他の設定**] の横にある [ **Exchange プロパティの編集**] を選択します。
    
3. ユーザーのメールボックスページで、左側のナビゲーションにある [* * メールボックスの機能] を選択し、[**訴訟ホールド**] の下の [**有効にする**] リンクを選択します。
    
4. [**訴訟**ホールド] ダイアログボックスで、[**訴訟ホールド期間**] フィールドに訴訟ホールド期間を指定することができます。無限に保持する場合は、フィールドを空のままにします。 また、メモを追加して、メールボックスの所有者を web サイトに誘導することもできます。 \>これにより、訴訟ホールドの**保存**について詳細に説明する必要があります。
    
**保持:** 保持期間の終了時に、特定の時間だけ保持したり、コンテンツを完全に削除したりするために、カスタマイズされた保持ポリシーを有効にすることができます。 詳細については、「[アイテム保持ポリシーの概要](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)」を参照してください。

## <a name="set-up-azure-information-protection-features"></a>Azure Information Protection 機能をセットアップする

Azure Information Protection (AIP) は、ラベルを適用することにより、ドキュメントや電子メールを分類し、必要に応じて保護します。 ラベルは、ルールと条件を定義する管理者、またはユーザーによって手動で、またはユーザーに推奨事項を与える組み合わせを使用して、自動的に適用できます。

Web 上の Outlook では、次の組み込みのラベルと制限を電子メールに適用できます。
  
- **転送不可**: 受信者はメッセージを読み取ることはできますが、コンテンツを転送、印刷、またはコピーすることはできません
    
- **Encrypt**: メッセージ全体が暗号化されます。 暗号化されたコンテンツにアクセスする前に自分の id を確認する必要があり、暗号化を削除することはできません。
    
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
