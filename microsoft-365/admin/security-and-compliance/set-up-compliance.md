---
title: ユーザーの脅威保護を強化Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: コンプライアンス機能を設定して、データ損失を防止し、お客様と顧客の機密情報を安全に保ちます。
ms.openlocfilehash: 09e9e0fda6969cc89a4eb6b5a106e7db5166e869
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60178097"
---
# <a name="set-up-compliance-features"></a>コンプライアンス機能をセットアップする

ユーザー Microsoft 365 Business Premiumデータとデバイスを保護し、ユーザーと顧客の機密情報を安全に保つ機能が付属しています。

## <a name="set-up-dlp-features"></a>DLP 機能のセットアップ

個人 [データの損失から保護する](../../compliance/create-a-dlp-policy-from-a-template.md) ポリシーを設定する方法の例については、「テンプレートから DLP ポリシーを作成する」を参照してください。 
  
DLP には、多くの異なる地域ですぐに使用できるポリシー テンプレートが多数付属しています。 たとえば、オーストラリアの財務データ、カナダの個人情報法、米国の財務データなどです。 完全 [なリストについては、「DLP ポリシー テンプレートに含まれる](../../compliance/what-the-dlp-policy-templates-include.md) もの」を参照してください。 これらのテンプレートはすべて、PII テンプレートの例と同様に有効にできます。 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>メールの保持を設定するには、Exchange Online Archiving

 **Exchange Online Archiving** 機能は、電子情報開示用の電子メール コンテンツを保持することで、コンプライアンスと規制の標準を維持するのに役立ちます。 また、訴訟が発生した場合のリスクを軽減し、セキュリティ侵害後または削除済みアイテムを回復する必要がある場合にデータを回復する方法を提供します。 訴訟ホールドを使用して、すべてのユーザーのコンテンツを保持したり、保持ポリシーを使用して保持する内容をカスタマイズすることができます。
  
**訴訟ホールド:** ユーザーのメールボックス全体を訴訟ホールドに設定することで、削除済みアイテムを含むすべてのメールボックス コンテンツを保持できます。 
    
メールボックスを訴訟ホールドに設定するには、管理センターで次の処理を行います。
    
1. 左側のナビゲーションで、[ユーザーのアクティブな **ユーザー]** \> **に移動します**。
    
2. 訴訟ホールドにメールボックスを配置するユーザーを選択します。 ユーザー ウィンドウで、[メールの設定]**を展開** し、[その他の設定] の横にある **[プロパティ** の編集] Exchange **します**。
    
3. ユーザーのメールボックス ページで、左側のナビゲーションで ** メールボックス機能 ** を選択し、[訴訟ホールド] の [有効にする] リンク **を選択します**。
    
4. [訴訟 **ホールド] ダイアログ** ボックスで、[訴訟ホールド期間] フィールドで訴訟ホールド **期間を指定** できます。 無限ホールドを設定する場合は、フィールドを空のままにします。 メモを追加して、訴訟ホールドの詳細を説明する必要がある Web サイトにメールボックスの所有者を指示できます。 \>**保存 .**
    
**保持:** たとえば、カスタマイズした保持ポリシーを有効にして、特定の時間保持したり、保持期間の終わりにコンテンツを完全に削除したりできます。 詳細については、「アイテム保持ポリシー [の概要」を参照してください](../../compliance/retention.md)。

## <a name="set-up-sensitivity-labels"></a>[感度ラベルの設定]

感度ラベルには、Azure Information Protection (AIP) プラン 1 が付き、ラベルを適用してドキュメントと電子メールを分類し、必要に応じて保護するのに役立ちます。 ラベルは、ルールと条件を定義する管理者、ユーザーが手動で、またはユーザーに推奨される組み合わせを使用して自動的に適用できます。

[感度ラベル] を設定するには、[感度 [ラベルの作成と管理] ビデオを表示](../../business-video/create-sensitivity-labels.md) します。



### <a name="install-the-azure-information-protection-client-manually"></a>Azure Information Protection クライアントを手動でインストールする

AIP クライアントを手動でインストールするには、次の手順を実行します。

1. Microsoft **ダウンロードAzinfoProtection_UL.exe** ダウンロード [センターからダウンロードします](https://www.microsoft.com/download/details.aspx?id=53018)。
 
2. Word ドキュメントを表示し、[ホーム] タブで [感度] オプションを使用して、インストールが機能したと **確認** できます。
<br/>![Word ドキュメントの [保護] タブ のドロップダウン。](../../media/word-sensitivity.png)

詳細については、「クライアントのインストール [」を参照してください](/azure/information-protection/infoprotect-tutorial-step3)。