---
title: Microsoft 365 Business Premium の脅威保護を強化する
f1.keywords:
- NOCSH
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
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
description: コンプライアンス機能を設定して、データの損失を防ぎ、顧客の機密情報を安全に保つことができます。
ms.openlocfilehash: 523d020587bcf16e46263b88ee7654b9c786e7a2
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048067"
---
# <a name="set-up-compliance-features"></a>コンプライアンス機能をセットアップする

Microsoft 365 Business Premium には、データとデバイスを保護するための機能が付属しており、お客様の機密情報を安全に保つために役立ちます。

## <a name="set-up-dlp-features"></a>DLP 機能を設定する

個人を特定できる情報 (PII) を保護するポリシーを設定する方法の例については、「[テンプレートからの DLP ポリシーの作成](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369)」を参照してください。 
  
DLP には、さまざまなロケールに対して、多くの使用可能なポリシーテンプレートが用意されています。 たとえば、オーストラリアの財務データ、カナダの個人情報法、米国金融データなど。 完全なリストについては[、DLP ポリシーテンプレートに含まれるもの](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a)を参照してください。 これらのテンプレートはすべて、PII テンプレートの例と同様に有効にすることができます。 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Exchange Online アーカイブを使用したメールの保存期間の設定

 **Exchange Online のアーカイブ**ライセンス機能は、電子情報開示用の電子メールコンテンツを保持することで、コンプライアンスおよび規制基準を維持するのに役立ちます。 また、訴訟が発生した場合にリスクを軽減し、セキュリティ違反が発生した後や、削除済みアイテムを復元する必要があるときに、データを回復するための手段を提供することもできます。 訴訟ホールドを使用して、ユーザーのすべてのコンテンツを保持するか、保持ポリシーを使用して、保持する内容をカスタマイズできます。
  
**訴訟ホールド:** ユーザーのメールボックスを訴訟ホールドの対象にすることで、削除されたアイテムを含むすべてのメールボックスのコンテンツを保持できます。 
    
メールボックスを訴訟ホールドの対象にするには、管理センターで次のようにします。
    
1. 左側のナビゲーションで、[**ユーザー** \> ] [**アクティブなユーザー**] に移動します。
    
2. 訴訟ホールドの対象とするメールボックスを持つユーザーを選択します。 ユーザーウィンドウで [メールの**設定**] を展開し、[**その他の設定**] の横にある [ **Exchange プロパティの編集**] を選択します。
    
3. ユーザーのメールボックスページで、左側のナビゲーションにある [* * メールボックスの機能] を選択し、[**訴訟ホールド**] の下の [**有効にする**] リンクを選択します。
    
4. [**訴訟**ホールド] ダイアログボックスで、[**訴訟ホールド期間**] フィールドに訴訟ホールド期間を指定できます。 無限の保持を配置する場合は、フィールドを空のままにします。 また、メモを追加してメールボックスの所有者を web サイトに誘導することもできます。これにより、訴訟ホールドの詳細を説明する必要があります。 \>**保存**します。
    
**保持:** 保持期間の終了時に、特定の時間だけ保持したり、コンテンツを完全に削除したりするために、カスタマイズされた保持ポリシーを有効にすることができます。 詳細については、「[アイテム保持ポリシーの概要](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)」を参照してください。

## <a name="set-up-sensitivity-labels"></a>機密ラベルを設定する

機密ラベルには、Azure Information Protection (AIP) プラン1が付属しており、ラベルを適用することによってドキュメントや電子メールを分類し、必要に応じて保護することができます。 ラベルは、ルールと条件を定義する管理者、またはユーザーによって手動で、またはユーザーに推奨事項を与える組み合わせを使用して、自動的に適用できます。

機密ラベルを設定するには、「[感度ラベルを作成して管理](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)する」のビデオを参照してください。



### <a name="install-the-azure-information-protection-client-manually"></a>Azure Information Protection クライアントを手動でインストールする

AIP クライアントを手動でインストールするには、次のようにします。

1. [Microsoft ダウンロードセンター](https://www.microsoft.com/download/details.aspx?id=53018)から**AzinfoProtection_UL .exe**をダウンロードします。
 
2. Word 文書を表示し、[**ホーム**] タブで [**秘密度**] オプションが有効になっていることを確認することで、インストールが正常に行われたことを確認できます。
<br/>![Word 文書内の [保護] タブのドロップダウン](../media/word-sensitivity.png)

詳細については、「[クライアントをインストールする](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)」を参照してください。
