---
title: Microsoft Defender 脅威インテリジェンスでのタグの使用 (Defender TI)
Description: このハウツー記事では、タグの種類と、Microsoft Defender 脅威インテリジェンス (Defender TI) でカスタム タグを追加、変更、削除、検索する方法について説明します。
author: alexroland24
ms.author: aroland
ms.service: threat-intelligence
ms.topic: how-to
ms.date: 08/02/2022
ms.custom: template-how-to
ms.openlocfilehash: 7dbf52dd3d1f08d9c5321874a54db48b7ef2e835
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2022
ms.locfileid: "67108532"
---
# <a name="using-tags"></a>タグの使用
Microsoft Defender 脅威インテリジェンス (Defender TI) タグは、システムによって派生した場合でも、他のユーザーによって生成された場合でも、成果物に関する迅速な分析情報を提供するために使用されます。 タグは、分析を改善するために、アナリストが現在のインシデントと調査とその履歴コンテキストの間のドットを接続する際に役立ちます。

Defender TI プラットフォームには、システム タグとカスタム タグの 2 種類のタグが用意されています。

![タグ Chrome HomePage の使用](media/UsingTagsChromeHomePage.png)

## <a name="prerequisites"></a>前提条件

- Azure Active Directory または個人用 Microsoft アカウント。 [アカウントにログインまたは作成する](https://signup.microsoft.com/)
- Microsoft Defender 脅威インテリジェンス (Defender TI) Premium ライセンス。
    > [!NOTE]
    > Defender TI Premium ライセンスを持たないユーザーは、Defender 脅威インテリジェンス ポータルにログインし、無料の Defender TI オファリングにアクセスできます。

## <a name="system-tags"></a>システム タグ

これらのタグは、ユーザーが分析をガイドするためにプラットフォームによって自動的に生成され、ユーザーの一部に入力や作業は必要ありません。

システム タグには、次のものが含まれます。

- **ルーティング可能:** 成果物にアクセス可能であることを示します。
- **ASN: IP アドレス ASN** の説明の省略部分をタグに取り込み、アナリストに IP アドレスが属するユーザーにコンテキストを提供します。
- **動的:** ドメインが、No-IP や Change IP などの動的 DNS サービスによって所有されているかどうかを示します。
- **シンクホール:** IP アドレスは、セキュリティ組織が攻撃キャンペーンを調査するために使用する研究シンクホールであるため、関連付けられているドメインは相互に直接接続されないことを示します。

![タグ システム](media/tagsSystem.png)

## <a name="custom-tags"></a>カスタム タグ

Defender TI 内のカスタム タグを使用して、侵害のインジケーター (IOC) にコンテキストを取り込み、パブリック レポートから不適切と知られているドメインや、会社のアナリストによって分類されたドメインを特定することで、分析をさらに簡単にします。 これらのタグは、独自の調査に基づいてユーザーによって手動で作成されます。 これらのタグを使用すると、ユーザーはアーティファクトに関する重要な分析情報をテナント内の他の Defender TI Premium ライセンス ユーザーと共有できます。

![タグ カスタム](media/tagsCustom.png)

## <a name="adding-modifying-and-removing-tags"></a>タグの追加、変更、および削除

ユーザーは、カスタム独自のタグをタグ バーに入力してタグ クラスターに追加できます。 これらのタグは、組織が Defender TI の顧客である場合、個々のユーザーとユーザーのチーム メンバーに表示できます。 システムに入力されたタグはプライベートであり、大規模なコミュニティと共有されません。

ユーザーがタグを追加できるように、タグを変更または削除することもできます。 ユーザーがタグを追加した後は、その同じユーザーまたはエンタープライズ組織内の別の有料ライセンスユーザーによって、タグを変更または削除できます。 これにより、セキュリティ チーム間での簡単なコラボレーションが可能になります。

1. [Defender 脅威インテリジェンス ポータル](https://ti.defender.microsoft.com/)にアクセスします。
2. ポータルにアクセスするための Microsoft 認証を完了します。
3. タグを追加する脅威インテリジェンス検索バーでインジケーターを検索します。

    ![タグ検索](media/tagsSearch.png)

4. Defender TI ポータルの左上隅にある [タグの編集] ドロップダウンを選択します。

    ![タグ 検索編集タグ](media/tagsSearchEditTags.png)

5. このインジケーターに関連付けるタグを追加します。

    > [!Note]
    > Tab キーを押して新しいインジケーターを追加します。

    ![Tags Search Add Tags](media/tagsSearchAddTags.png)

6. すべてのタグが追加されたら、[保存] ボタンを選択して変更を保存します。

    ![Tags Search Save Tags](media/tagsSearchSaveTags.png)

7. タグを編集するには、手順 3. を繰り返します。 タグ名の末尾にある [X] を選択するか、手順 4. で行ったように新しいタグを追加して、タグを削除します。

8. 変更内容を保存します。

    ![タグ 検索タグ](media/tagsSearchTags.png)

## <a name="viewing-and-searching-tags"></a>タグの表示と検索

ユーザーは、IP、ドメイン、またはホストアーティファクトを検索した後、自分またはテナント内の他のユーザーによって追加されたタグを表示できます。

![タグ カスタム](media/tagsCustom.png)

1. [Defender 脅威インテリジェンス ポータル](https://ti.defender.microsoft.com/)にアクセスします。
2. ポータルにアクセスするための Microsoft 認証を完了します。
3. ユーザーは、Defender TI の脅威インテリジェンス検索を使用してカスタム タグを検索するには、脅威インテリジェンス検索バーのドロップダウンでタグ検索の種類を選択し、タグ値を検索して、同じタグ値を共有する他のすべてのインジケーターを識別します。

    ![検索タグ](media/searchTag.png)

一般的なタグのユース ケース ワークフロー トリアージ アナリストがインシデントを調査し、それがフィッシングに関連していることを見つけたとします。 そのアナリストは、そのインシデントに関連する侵害のインジケーターにタグとして "フィッシング" を追加できます。 その後、インシデント対応と脅威検出チームは、これらの侵害の指標をさらに分析し、サイバー脅威インテリジェンスに対応するユーザーと連携して、フィッシング インシデントの原因となったアクター グループを特定できます。 その後、侵害のインジケーターや、"[SHA-1 ハッシュ]" カスタム タグなどの他の関連する侵害インジケーターに接続されたインフラストラクチャに別の "[アクター名]" タグを追加できます。

## <a name="next-steps"></a>次の手順

詳細については、以下を参照してください。

- [Microsoft Defender 脅威インテリジェンス (Defender TI)とは何ですか?](what-is-microsoft-defender-threat-intelligence-defender-tI.md)
- [データ セット](data-sets.md)
- [データの並べ替え、フィルター処理、ダウンロード](sorting-filtering-and-downloading-data.md)
- [評判スコアリング](reputation-scoring.md)
- [アナリストの分析情報](analyst-insights.md)
- [プロジェクトの使用](using-projects.md)