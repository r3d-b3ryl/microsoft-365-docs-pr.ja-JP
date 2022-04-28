---
title: エンタープライズ テスト環境のMicrosoft 365のデータ分類
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: M365-security-compliance
ms.custom:
- Ent_TLGs
- admindeeplinkMAC
- admindeeplinkDEFENDER
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテスト ラボ ガイドを使用して、エンタープライズ テスト環境のMicrosoft 365内のドキュメントに保持ラベルを作成して使用します。
ms.openlocfilehash: f5bcde88be148ed883b4ad10e3b8116ed21c9fa8
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096812"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ テスト環境のMicrosoft 365のデータ分類

*このテスト ラボ ガイドは、エンタープライズ環境とOffice 365 Enterpriseテスト環境の両方のMicrosoft 365に使用できます。*

この記事では、エンタープライズ テスト環境のMicrosoft 365で保持ラベルを使用してデータ分類を構成する方法について説明します。

テスト環境でデータを分類するには、次の 3 つのフェーズが含まれます。
- [フェーズ 1: エンタープライズ テスト環境のMicrosoft 365を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: 保持ラベルを作成する](#phase-2-create-retention-labels)
- [フェーズ 3: 保持ラベルをドキュメントに適用する](#phase-3-apply-retention-labels-to-documents)

![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックのMicrosoft 365のすべての記事へのビジュアル マップについては、エンタープライズ テスト ラボ ガイド [スタックのMicrosoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)に関するページを参照してください。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境のMicrosoft 365を構築する

最小要件を持つ軽量な方法で保持ラベルを構成するだけの場合は、「 [Lightweight 基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従います。
  
シミュレートされたエンタープライズで保持ラベルを構成する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。
  
> [!NOTE]
> テスト保持ラベルには、シミュレートされたエンタープライズ テスト環境は必要ありません。これには、インターネットに接続されたシミュレートされたイントラネットと、Active Directory Domain Services (AD DS) フォレストのディレクトリ同期が含まれます。 ここでは、自動化されたライセンスとグループ メンバーシップをテストし、一般的な組織を表す環境で実験できるように、オプションとして提供されています。

## <a name="phase-2-create-retention-labels"></a>フェーズ 2: 保持ラベルを作成する

このフェーズでは、SharePoint Online ドキュメント フォルダーのさまざまな保持レベルの保持ラベルを作成します。

1. グローバル管理者アカウントを<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">使用して、Microsoft 365 Defender ポータル</a>にサインインします。
1. ブラウザーの [**ホーム - Microsoft 365 セキュリティ**] タブで、[**ClassificationRetention** >  ラベル] を選択します。
1. [**ラベルを作成**] を選択します。
1. [**ラベルの名前]** ウィンドウで、[ラベルの **名前**] に「**内部パブリック」** と入力し、[**次へ**] を選択します。
1. [ **ファイル プラン記述子** ] ウィンドウで、[ **次へ**] を選択します。
1. [ **ラベルの設定** ] ウィンドウで、必要に応じて [ **保持期間]** を **[オン]** に設定し、[ **次へ**] を選択します。
1. [ **設定の確認** ] ウィンドウで、[ **ラベルの作成**] を選択します。
1. 次の名前の追加ラベルについて、手順 3 から 7 を繰り返します。
  - プライベート
  - 機密
  - 非常に機密性の高い社外秘
1. [ **保持ラベル** ] ウィンドウで、[ **ラベルの発行**] を選択します。
1. [ **発行するラベルの選択]** ウィンドウで、[ **発行するラベルの選択**] を選択します。
1. [ **ラベルの選択** ] ウィンドウで、[ **追加** ] を選択し、4 つのラベルをすべて選択します。
1. [ **追加]** を選択し、[完了] を選択 **します**。
1. [ **発行するラベルの選択]** ウィンドウで、[ **次へ**] を選択します。
1. [ **場所の選択** ] ウィンドウで、[ **次へ**] を選択します。
1. [**ポリシーの名前]** ウィンドウで、「名前」に「**組織の例****」** と入力し、[**次へ**] を選択します。
1. [ **設定の確認** ] ウィンドウで、[ **ラベルの発行**] を選択します。
 
保持ラベルが発行されるまで数分かかる場合があります。

## <a name="phase-3-apply-retention-labels-to-documents"></a>フェーズ 3: 保持ラベルをドキュメントに適用する

このフェーズでは、SharePoint Online サイトの Documents フォルダー内のファイルの既定の保持ラベルの動作を検出し、ドキュメントの保持ラベルを手動で変更します。

まず、オンライン チーム サイトSharePoint機密レベルを作成します。
  
1. ブラウザーのプライベート インスタンスを使用して、グローバル管理者アカウントを使用して<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>にサインインします。
1. タイルの一覧で、**SharePoint** を選択します。
1. ブラウザーの新しい **[SharePoint**] タブで、[**サイトの作成**] を選択します。
1. **[サイトの作成]** ページで、**[チーム サイト]** を選択します。
1. [ **チーム サイト名** ] ボックスに「 **SensitiveFiles**」と入力します。
1. [**チーム サイトの説明**] ボックス **に、「機密ファイルのサイトSharePoint入力します**。
1. [ **プライバシーの設定**] で、[ **プライベート- メンバーのみがこのサイトにアクセスできる**] を選択し、[ **次へ**] を選択します。
1. **[追加するWho**] ウィンドウで、[完了] を選択 **します**。
    
次に、機密保持ラベル用に SensitiveFiles チーム サイトの Documents フォルダーを構成します。
  
1. ブラウザーの [ **SensitiveFiles** ] タブで、[ **ドキュメント**] を選択します。
1. **設定** アイコンを選択し、[**ライブラリの設定**] を選択します。
1. [ **アクセス許可と管理**] で、[ **このリストまたはライブラリ内のアイテムにラベルを適用** する] を選択します。 このオプションが表示されない場合、保持ラベルはまだ発行されません。 後でこの手順を試してください。
1. **[設定- ラベルの適用**] で、ドロップダウン ボックスで **[機密**] を選択し、[保存] を選択 **します**。

次に、SensitiveFiles サイトに新しいドキュメントを作成し、保持ラベルを変更します。
    
1. ドキュメント フォルダーで、**NewWord ドキュメント****を** > 選択します。
1. 空白の文書にテキストを入力します。 テキストが保存されるまで待ちます。
1. メニュー バーで、[ **共有ドキュメント**] を選択します。
1. **Document.docx** ファイル名の横にある縦の省略記号を選択し、[詳細] を選択 **します**。
1. 右側のウィンドウの [ **プロパティ** ] セクションの [ **保持ラベルの適用**] で、ドキュメントに **機密** 保持ラベルが自動的に適用されていることに注意してください。
1. [**すべて編集**] をクリックします。
1. **[Document.docx**] ウィンドウの [**保持ラベルの適用**] で[**極秘**] ラベルを選択し、[保存] を選択 **します**。

## <a name="next-step"></a>次の手順

テスト環境の [追加情報保護機能](m365-enterprise-test-lab-guides.md#information-protection) と機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)
