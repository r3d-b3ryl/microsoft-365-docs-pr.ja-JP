---
title: Microsoft 365 for enterprise テスト環境のデータ分類
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテストラボガイドを使用して、Microsoft 365 for enterprise テスト環境のドキュメントに対して保持ラベルを作成して使用します。
ms.openlocfilehash: 171fcb74b09a1f2e5c80f23e010640dce55660bc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686408"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Microsoft 365 for enterprise テスト環境のデータ分類

*このテストラボガイドは、Microsoft 365 for enterprise および Office 365 エンタープライズテスト環境の両方で使用できます。*

この記事の手順に従って、エンタープライズテスト環境の Microsoft 365 で保持ラベルを使用してデータ分類を構成します。

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [ここ](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事へのビジュアル マップを確認してください。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する

最小要件での軽量な方法で保持ラベルを構成する場合は、「 [軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで保持ラベルを構成する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。
  
> [!NOTE]
> 保持ラベルのテストでは、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと、Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。 

## <a name="phase-2-create-retention-labels"></a>フェーズ 2: 保持ラベルを作成する

このフェーズでは、SharePoint Online ドキュメントフォルダーのさまざまな保持レベルの保持ラベルを作成します。

1. グローバル管理者アカウントを使用して、 [Microsoft 365 セキュリティセンター](https://security.microsoft.com/homepage) にサインインします。
    
2. ブラウザーの [ **ホーム-Microsoft 365 セキュリティ** ] タブで、[ **> 保持ラベルの分類**] をクリックします。
    
3. **[ラベルの作成]** をクリックします。
    
4. [**ラベルに名前**をつける] ウィンドウで、[**ラベルに名前**を付ける] に「 **Internal Public** 」と入力し、[**次へ**] をクリックします。

5. [ **ファイル計画記述子** ] ウィンドウで、[ **次へ**] をクリックします。
    
6. [ **ラベル設定** ] ウィンドウで必要に応じて、[ **保持** ] を **[オン**] に設定し、[ **次へ**] をクリックします。
    
7. [ **設定の確認** ] ウィンドウで、[ **ラベルの作成**] をクリックします。
    
8. 次の名前の追加ラベルについて、手順 3 から 7 を繰り返します。
    
  - プライベート
    
  - 機密
    
  - 非常に機密性の高い社外秘
  
9. [ **保持ラベル** ] ウィンドウで、[ **ラベルの発行**] をクリックします。
    
10. [ **発行するラベルを選択** ] ウィンドウで、[ **発行するラベルを選択**] をクリックします。
    
11. [ **ラベルの選択** ] ウィンドウで、[ **追加** ] をクリックして4つすべてのラベルを選択します。
    
12. **[追加]** をクリックし、**[完了]** をクリックします。
    
13. **[発行するラベルを選択]** ウィンドウで、 **[次へ]** をクリックします。
    
14. **[場所の選択]** ウィンドウで、 **[次へ]** をクリックします。
    
15. **[ポリシーに名前をつける]** ウィンドウで、 **[名前]** に「 **サンプル組織**」と入力してから、 **[次へ]** をクリックします。
    
16. [ **設定の確認** ] ウィンドウで、[ **ラベルの発行**] をクリックします。
 
保持ラベルが公開されるまでに数分かかる場合があることに注意してください。

## <a name="phase-3-apply-retention-labels-to-documents"></a>フェーズ 3: ドキュメントに保持ラベルを適用する

このフェーズでは、SharePoint Online サイトの Documents フォルダー内のファイルの既定の保持ラベルの動作を検出し、ドキュメントの保持ラベルを手動で変更します。

最初に、機密レベルの SharePoint Online チームサイトを作成します。
  
1. ブラウザーのプライベートインスタンスを使用して、グローバル管理者アカウントを使用して [Microsoft 365 管理センター](https://admin.microsoft.com) にサインインします。
    
2. タイルのリストで、**[SharePoint]** をクリックします。
    
3. ブラウザーの新しい [ **SharePoint** ] タブで、[ **サイトの作成**] をクリックします。
    
4. **[サイトの作成]** ページで、**[チーム サイト]** をクリックします。
    
5. [ **チームサイト名**] に、「 **SensitiveFiles**」と入力します。
    
6. [ **チームサイトの説明**] に、「 **機密ファイル用の SharePoint サイト**」と入力します。
    
7.  **[プライバシー設定]** で、**[プライベート - メンバーのみがこのサイトにアクセス可能**」を選択して **[次へ]** をクリックします。
    
8. [ **誰を追加** しますか] ウィンドウで、[ **完了**] をクリックします。
    
次に、機密保持ラベル用に SensitiveFiles チームサイトのドキュメントフォルダーを構成します。
  
1. ブラウザーの [ **SensitiveFiles** ] タブで、[ **ドキュメント**] をクリックします。
    
2. [設定] アイコンをクリックしてから、**[ライブラリの設定]** をクリックします。
    
3. [ **権限と管理**] で、[ **このリストまたはライブラリ内のアイテムにラベルを適用] を**クリックします。 このオプションが表示されない場合、保持ラベルはまだ公開されていません。 後でこの手順を試してください。
    
4. [ **設定-ラベルの適用**] で、ドロップダウンボックスで [ **機密** ] を選択し、[ **保存**] をクリックします。

次に、SensitiveFiles サイトで新しいドキュメントを作成し、そのアイテム保持ラベルを変更します。
    
1. Documents フォルダーで、[ **新しい > Word 文書**] をクリックします。
    
2. 空白のドキュメントにテキストを入力します。 テキストが保存されるまで待機します。
    
3. メニューバーで、[ **共有ドキュメント**] をクリックします。
    
4. **Document.docx**ファイル名の横にある縦の省略記号をクリックし、[**詳細**] をクリックします。
    
5. 右側のウィンドウの [ **プロパティ** ] セクションの [ **保持ラベルの適用**] で、ドキュメントに **機密** 保持ラベルが自動的に適用されている点に注意してください。
    
6. [**すべて編集**] をクリックします。
    
7. **Document.docx**ウィンドウで、[**保持ラベルの適用**] の下の [**高機密**] ラベルを選択し、[**保存**] をクリックします。

## <a name="next-step"></a>次の手順

テスト環境でのその他の [情報保護](m365-enterprise-test-lab-guides.md#information-protection) 機能と機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[エンタープライズドキュメントの Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)

 
