---
title: エンタープライズ テスト環境Microsoft 365データ分類
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
description: このテスト ラボ ガイドを使用して、エンタープライズ テスト環境のドキュメントに保持ラベルを作成Microsoft 365使用します。
ms.openlocfilehash: 79002397be7c44c5c160d80288d3fea6e9c1f9594a024f5aa4dc501f86dda886
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53891321"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ テスト環境Microsoft 365データ分類

*このテスト ラボ ガイドは、エンタープライズ環境とテスト環境Microsoft 365両方Office 365 Enterprise使用できます。*

この記事では、エンタープライズ テスト環境で保持ラベルを使用してデータMicrosoft 365構成する方法について説明します。

テスト環境でのデータの分類には、次の 3 つのフェーズがあります。
- [フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: 保持ラベルの作成](#phase-2-create-retention-labels)
- [フェーズ 3: ドキュメントに保持ラベルを適用する](#phase-3-apply-retention-labels-to-documents)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックの Microsoft 365 内のすべての記事への視覚的なマップについては、「Microsoft 365 テスト ラボ ガイド スタック」[を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する

最小限の要件で保持ラベルを軽量な方法で構成する場合は、「Lightweight 基本構成」の手順 [に従ってください](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
シミュレートされたエンタープライズで保持ラベルを構成する場合は、「パススルー認証」の手順 [に従います](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> 保持ラベルのテストでは、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメイン サービス (AD DS) フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズ テスト環境は必要とされません。 ここではオプションとして提供され、一般的な組織を表す環境で、自動ライセンスとグループ メンバーシップをテストして実験できます。

## <a name="phase-2-create-retention-labels"></a>フェーズ 2: 保持ラベルの作成

このフェーズでは、オンライン ドキュメント フォルダーに対するさまざまなレベルの保持SharePoint作成します。

1. グローバル管理者アカウントを[使用Microsoft 365セキュリティ センター](https://security.microsoft.com/homepage)にサインインします。
1. ブラウザーの **[ホーム - Microsoft 365セキュリティ**] タブで、[分類の保持ラベル]  >  **を選択します**。
1. [**ラベルを作成**] を選択します。
1. [ラベルに **名前を付け] ウィンドウで** 、[ラベルに名前を付け] に **「内部パブリック** 」と **入力** し、[次へ] を **選択します**。
1. [ファイルプラン **記述子] ウィンドウで、[** 次へ] を **選択します**。
1. [ラベルの **設定] ウィンドウ** で、必要に応じて [保持] を **[オン**] に設定し、[次へ] を **選択します**。
1. [設定 **の確認] ウィンドウで** 、[ラベルの **作成] を選択します**。
1. 次の名前の追加ラベルについて、手順 3 から 7 を繰り返します。
  - プライベート
  - 機密
  - 非常に機密性の高い社外秘
1. [保持ラベル **] ウィンドウで** 、[ラベルの発行] **を選択します**。
1. [発行する **ラベルの選択] ウィンドウで** 、[発行 **するラベルの選択] を選択します**。
1. [ラベルの **選択] ウィンドウで** 、[追加] **を選択し** 、4 つのラベルすべてを選択します。
1. [追加 **] を** 選択し、[完了] **を選択します**。
1. [発行する **ラベルの選択] ウィンドウで、[** 次へ] を **選択します**。
1. [場所の **選択] ウィンドウで、[** 次へ] を **選択します**。
1. [ポリシーに **名前を付け] ウィンドウで**、[名前] に「**組織の例**」と入力し、[次へ] を **選択します**。 
1. [設定 **の確認] ウィンドウで、[** ラベルの発行] **を選択します**。
 
保持ラベルが発行されるには数分かかる場合があります。

## <a name="phase-3-apply-retention-labels-to-documents"></a>フェーズ 3: ドキュメントに保持ラベルを適用する

このフェーズでは、SharePoint Online サイトの Documents フォルダーにあるファイルの既定の保持ラベルの動作を検出し、ドキュメントの保持ラベルを手動で変更します。

まず、オンライン チーム サイトに機密レベルSharePoint作成します。
  
1. ブラウザーのプライベート インスタンスを使用して、グローバル[管理者アカウントを使用](https://admin.microsoft.com)Microsoft 365 管理センターにサインインします。
1. タイルの一覧で、[タイル] を **SharePoint。**
1. ブラウザーの [新 **SharePoint]** タブで、[サイトの作成]**を選択します**。
1. **[サイトの作成]** ページで、**[チーム サイト]** を選択します。
1. [チーム サイト **名] ボックスに****「SensitiveFiles」と入力します**。
1. [チーム サイト **の説明] ボックス** に、機密 **ファイルSharePointサイトを入力します**。
1. [ **プライバシーの設定]** で、[ **プライベート] を選択し、メンバー** だけがこのサイトにアクセスし、[次へ] を **選択します**。
1. [追加 **Who] ウィンドウで、[完了]** を **選択します**。
    
次に、SensitiveFiles チーム サイトの [ドキュメント] フォルダーを [機密性の高い保持] ラベル用に構成します。
  
1. ブラウザーの **[SensitiveFiles]** タブで、[ドキュメント] **を選択します**。
1. [設定]**設定** を選択し、[ライブラリの設定]**を選択します**。
1. [ **アクセス許可と管理] で**、[このリスト **またはライブラリ内のアイテムにラベルを適用する] を選択します**。 このオプションが表示されない場合、保持ラベルはまだ発行されません。 後でこの手順を試してください。
1. **[設定ラベルの適用] で**、ドロップダウン ボックス **で**[機密] を選択し、[保存] を **選択します**。

次に、SensitiveFiles サイトに新しいドキュメントを作成し、保持ラベルを変更します。
    
1. ドキュメント フォルダーで、[新しい Word 文書 **]**  >  **を選択します**。
1. 空白の文書にテキストを入力します。 テキストが保存されるのを待ちます。
1. メニュー バーで、[共有ドキュメント] **を選択します**。
1. ファイル名の **横Document.docx、** 垂直省略記号を選択し、[詳細] を **選択します**。
1. 右側のウィンドウの [プロパティ]**セクションの**[保持ラベルの適用] で、ドキュメントに [機密保持ラベル] が自動的に適用 **された点に** 注意してください。 
1. [**すべて編集**] をクリックします。
1. [保存]**ウィンドウDocument.docx** [保持ラベルの **適用] で、[** 機密性の高いラベル] を選択し、[保存] を **選択します**。 

## <a name="next-step"></a>次の手順

テスト環境 [の追加情報保護](m365-enterprise-test-lab-guides.md#information-protection) 機能と機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)