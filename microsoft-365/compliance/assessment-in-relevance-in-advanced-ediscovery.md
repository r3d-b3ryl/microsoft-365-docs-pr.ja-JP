---
title: 高度な電子情報開示の関連性の評価を理解する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: Microsoft 365 Advanced eDiscovery の関連トレーニングにおいて、さまざまな問題を特定するための評価ステージとその役割についての概要を説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: afd4f1f549d52652ac02cfa410efc507ece58910
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818416"
---
# <a name="understand-assessment-in-relevance-in-advanced-ediscovery-classic"></a>高度な電子情報開示で関連性のある評価を理解する (クラシック)

> [!NOTE]
> Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
上級電子情報開示では、たとえば定義済みの問題とケースに対してインポートされたデータについて、早期に評価することができます。 上級電子情報開示を使用すると、エキスパートは採用されたアプローチを決定し、ドキュメントレビュープロジェクトにこれらの決定を適用することができます。
  
## <a name="understanding-assessment"></a>評価について

評価では、専門家は少なくとも500のファイルのランダムセットをレビューします。これは、問題の豊富さを特定し、トレーニング結果を反映するために統計情報を生成するために使用されます。 詳細な電子情報開示の関連性を向上させるために詳細な電子情報開示の関連性を向上させる統計レベルに達すると、評価は成功します。 
  
評価セット内の関連ファイルの数が多いほど、安定性アルゴリズムの統計と効果が正確になります。 評価ファイル内の関連ファイルの数は、その問題の豊富さに依存します。 多様性は、懸案事項に関連する設定の関連ファイルの予想パーセンテージです。 低コストの問題よりも、より高いレベルの関連ファイルをより多く使用すると、低低の問題よりも高速になります。 非常に低い (たとえば2% 以下の) 豊富な問題については、膨大な数の関連ファイルを獲得するために非常に大きな評価を設定する必要があります。
  
この統計情報は、トレーニング中に [追跡] タブと [決定] タブに表示されます。また、バッチ計算後には、さまざまなレビューセットに対する呼び戻しの見積もりを含みます。 Statistics では、サンプルセット (この例では評価ファイル) に基づく見積もりには、エラーの余白と、その誤差範囲の信頼度レベルが含まれています。 たとえば、80% の予想リコールは、信頼レベルが95% で、プラスまたはマイナス5% の誤差がある可能性があります。 これは、推定される呼び戻しは実際には 75%-85% で、この推定は95% の信頼度があることを意味します。 評価セットが大きいほど、エラーの余白が小さくなり、統計値がより正確になります。 
  
専門家が500ファイルの初期評価セットをレビューした後、関連性によって、呼び戻し値の現在のエラーのマージンを特定することができます。 また、評価セットを最適化するために、既定のエラーの許容範囲を設定することも推奨されます。 次に例を示します。
  
- 評価セットで既にプラスまたはマイナス10% の誤差が得られている場合は、トレーニングへの移行をお勧めします (追加の評価レビューは必要ありません)。 
    
- 評価セットでプラスまたはマイナス13% の誤差が得られた場合は、別の評価ファイルのセットをレビューして、より小さな余白に到達することをお勧めします。 
    
- 豊富な機能が非常に低い場合は、エラーの許容範囲を超えている場合でも、評価を停止することをお勧めします (統計値が実用的でない場合)。
    
各問題には、さまざまな豊富なエラーがあり、その結果として予測される追加評価ファイルの推定数が表示されます。 次の評価セットは、最大ファイル数 (1 つのセット内の最大 1000) に従って作成されます。
  
必要に応じて、関連性に関する推奨事項を受け入れるか、または現在の誤差の余白を調整することができます。 既定のエラーの現在のマージンは、「呼び戻し」では、75% 以上であることが確認されます。
  
> [!NOTE]
> 問題が発生した場合は、展開されたビューの [**関連性の \> 追跡**] タブで、問題ごとに [**評価**] チェックボックスをオフにし、次に [すべての問題] を選択して、評価ステージをバイパスできます。 そのため、この問題に関する統計情報はありません。 [**評価**] チェックボックスをオフにする > は、評価が実行される前にのみ実行できます。 複数の問題が存在する場合は、各問題のチェックボックスがオフになっている場合にのみ評価が省略されます。 
  
## <a name="related-topics"></a>関連項目

[Advanced eDiscovery (クラシック)](office-365-advanced-ediscovery.md)
  
[タグ付けと評価](tagging-and-assessment-in-advanced-ediscovery.md)
  
[タグ付けと関連性トレーニング](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[関連性分析の追跡](track-relevance-analysis-in-advanced-ediscovery.md)
  
[結果に基づいて決定する](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[関連性分析のテスト](test-relevance-analysis-in-advanced-ediscovery.md)

