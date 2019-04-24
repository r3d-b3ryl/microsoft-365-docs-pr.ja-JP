---
title: Microsoft 365 Enterprise テスト環境のデータ分類
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテストラボガイドを使用して、Microsoft 365 エンタープライズテスト環境のドキュメントに対して Office 365 保持ラベルを作成して使用します。
ms.openlocfilehash: 3d64cd245e117813cb4c81a6e9099cd1a0120317
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283540"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise テスト環境のデータ分類

この記事の手順を使用して、Microsoft 365 エンタープライズテスト環境で Office 365 の保持ラベルを使用してデータ分類を構成します。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 Enterprise テスト環境を構築する

最小要件での軽量な方法で Office 365 の保持ラベルを構成する場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで Office 365 の保持ラベルを構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。
  
> [!NOTE]
> Office 365 の保持ラベルのテストでは、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。 

## <a name="phase-2-create-office-365-retention-labels"></a>フェーズ 2: Office 365 の保持ラベルを作成する

このフェーズでは、SharePoint Online ドキュメントフォルダーのさまざまな保持レベルの保持ラベルを作成します。

1. 全体管理者アカウントで、[Microsoft 365 コンプライアンス ポータル](https://compliance.microsoft.com)にサインインします。
    
2. ブラウザーの **[ホーム - Microsoft 365 コンプライアンス]** タブで、**[分類] > [ラベル]** をクリックします。
    
3. **[保持ラベル] > [ラベルの作成]** をクリックします。
    
4. **[ラベルに名前をつける]** ウィンドウで、**[ラベルに名前をつける]** のところに「**内部パブリック**」と入力してから、**[次へ]** をクリックします。

5. **[ファイル計画記述子]** ウィンドウで **[次へ]** をクリックします。
    
6. **[ラベルの設定]** ウィンドウで、必要に応じて **[保持]** を **[オン]** にして **[次へ]** をクリックします。
    
7. **[設定の確認]** ウィンドウで、**[ラベルを作成する]** をクリックします。
    
8. 次の名前のラベルについて、手順3-7 を繰り返します。
    
  - プライベート
    
  - 機密
    
  - 非常に機密性の高い社外秘
  
9. **[ホーム]、[ラベル]** ウィンドウで、**[Publish labels]\(ラベルの発行\)** をクリックします。
    
10. **[発行するラベルを選択]** ウィンドウで、 **[発行するラベルを選択]** をクリックします。
    
11. **[Choose labels]\(ラベルの選択\)** ウィンドウで、**[追加]** をクリックして 4 つのラベルをすべて選択します。
    
12. [ **完了**] をクリックします。
    
13. **[発行するラベルを選択]** ウィンドウで、 **[次へ]** をクリックします。
    
14. **[場所の選択]** ウィンドウで、 **[次へ]** をクリックします。
    
15. **[ポリシーに名前をつける]** ウィンドウで、 **[名前]** に「 **サンプル組織**」と入力してから、 **[次へ]** をクリックします。
    
16. **[設定の確認]** ウィンドウで、 **[ラベルの発行]** をクリックしてから **[閉じる]** をクリックします。
 
保持ラベルが公開されるまでに数分かかる場合があることに注意してください。

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a>フェーズ 3: ドキュメントに Office 365 の保持ラベルを適用する

このフェーズでは、SharePoint Online サイトの Documents フォルダー内のファイルの既定の保持ラベルの動作を検出し、ドキュメントの保持ラベルを手動で変更します。

最初に、機密レベルの SharePoint Online チームサイトを作成します。
  
1. ローカル コンピューターのブラウザーを使用して、全体管理者アカウントで [Office 365 ポータル](https://portal.office.com)にサインインします。
    
2. タイルのリストで、**[SharePoint]** をクリックします。
    
3. ブラウザーの新しい [ **SharePoint** ] タブで、[**サイトの作成**] をクリックします。
    
4. **[サイトの作成]** ページで、 **[チーム サイト]** をクリックします。
    
5. [**チームサイト名**] に、「 **SensitiveFiles**」と入力します。
    
6. [**チームサイトの説明**] に、「**機密ファイル用の SharePoint サイト**」と入力します。
    
7.  **[プライバシー設定]** で、 **[プライベート - メンバーのみがこのサイトにアクセス可能**」を選択して **[次へ]** をクリックします。
    
8. **[誰を追加しますか]** ウィンドウで、 **[完了]** をクリックします。
    
次に、機密保持ラベル用に SensitiveFiles チームサイトのドキュメントフォルダーを構成します。
  
1. ブラウザーの [ **SensitiveFiles** ] タブで、[**ドキュメント**] をクリックします。
    
2. [設定] アイコンをクリックしてから、 **[ライブラリの設定]** をクリックします。
    
3. **[権限と管理]** をクリックして、 **[このライブラリ内の項目にラベルを適用]** をクリックします。
    
4. [**設定-ラベルの適用**] で、ドロップダウンボックスで [**機密**] を選択し、[**保存**] をクリックします。

次に、SensitiveFiles サイトで新しいドキュメントを作成し、そのアイテム保持ラベルを変更します。
    
1. documents フォルダーで、[ **New > Word document**] をクリックします。
    
2. 空白のドキュメントにテキストを入力します。 テキストが保存されるまで待機します。
    
3. メニューバーで、[**共有ドキュメント**] をクリックします。
    
4. **文書の .docx**ファイル名の横にある Word アイコンをクリックします。
    
5. 右側のウィンドウの [**プロパティ**] セクションの [**保持ラベルの適用**] で、ドキュメントに**機密**ラベルが自動的に適用されていることに注意してください。
    
6. [**すべて編集**] をクリックします。
    
7. 文書の **.docx**ウィンドウの [ラベルの**適用**] で [**高機密**] ラベルを選択し、[**保存**] をクリックします。

Office 365 保持ラベルを運用環境に展開する方法の詳細とリンクについては、**情報保護**フェーズの「[環境の分類を構成](infoprotect-configure-classification.md)する」の手順を参照してください。

## <a name="next-step"></a>次の手順

テスト環境でのその他の[情報保護](m365-enterprise-test-lab-guides.md#information-protection)機能と機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)

 