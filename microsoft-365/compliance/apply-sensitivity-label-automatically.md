---
title: 機密ラベルをコンテンツに自動的に適用する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: 機密ラベルを作成する場合、ドキュメントまたは電子メールにラベルを自動的に割り当てるか、あるいは推奨するラベルを選択するようにユーザーに求めることができます。
ms.openlocfilehash: a1ea81bf8c65d3f54d26b19eae3b590f11283c30
ms.sourcegitcommit: 109b44aa71bb8453d0a602663df0fcf7ed7dfdbe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2020
ms.locfileid: "42277214"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a>機密ラベルをコンテンツに自動的に適用する

機密ラベルを作成する場合、機密情報が含まれている場合にそのラベルをコンテンツに自動的に割り当てるか、あるいは推奨するラベルを適用するようにユーザーに求めることができます。

機密ラベルを自動的にコンテンツに適用する機能が重要である理由は次のとおりです。

- ユーザーのトレーニングは、一部の分類方法についてのみ必要。

- ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。

- ユーザーはポリシーについて把握する必要がなくなり、自分たちの仕事に集中できます。

Windows 用 Office アプリの自動ラベル付けは、Azure Information Protection 統合ラベル付けクライアントでサポートされています。 Office アプリ組み込みのラベル付けでは、この機能が[一部のアプリでプレビュー](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)されています。

Office アプリの自動ラベル付け設定は、[機密ラベルを作成または編集する](create-sensitivity-labels.md)ときに使用できます。

![機密ラベルの自動ラベル付けオプション](../media/sensitivity-labels-auto-labeling-options.png)

## <a name="how-to-configure-auto-labeling-for-office-apps"></a>Office アプリの自動ラベル付けを構成する方法

機密ラベルの最も強力な機能の 1 つは、特定の条件に一致したコンテンツに自動的に機密ラベルを適用する能力です。 この場合、組織内のユーザーが機密ラベルを適用する必要はありません。これは Office 365 により自動的に行われます。

コンテンツに特定の種類の機密情報が含まれている場合、機密ラベルをコンテンツに自動的に適用することを選択できます。 機密情報の種類または分類子のリストから選択します。

![Office アプリの自動ラベル付けのラベル条件](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> 現在、**分類子** のオプションは制限付きプレビュー中であり、テナントでこの機能を有効にするには Microsoft にフォームを送信する必要があります。 詳細については、「[Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview (組み込みの分類子を使用した Office アプリの自動ラベル付けの発表 - 制限付きプレビュー)](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889)」のブログ投稿を参照してください。

この機密ラベルが自動的に適用されると、ユーザーの Office アプリに通知が表示されます。 [**OK**] をクリックして通知を閉じることができます。

![ドキュメントにラベルが自動適用されたという通知](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a>ラベルの機密情報の種類の構成

**機密情報の種類** オプションを選択すると、データ損失防止 (DLP) ポリシーを作成するときと同じ機密情報の種類の一覧が表示されます。 そのため、たとえば、クレジットカード番号や社会保障番号など、お客様の個人情報 (PII) を含むコンテンツに極秘ラベルを自動的に適用できます。

![Officeアプリの自動ラベル付け用の機密情報の種類](../media/sensitivity-labels-sensitive-info-types.png)

機密情報の種類を選択した後は、インスタンス数または一致精度を変更して条件を絞り込むことができます。 詳細については、「[一致の難易度を設定するためのルールの調整](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)」を参照してください。

さらに、条件で検知する必要があるのは、機密情報の種類のすべてか、またはそのうちの 1 つだけかを選択できます。 また、条件をより柔軟または複雑にするには、グループを追加し、グループ間で論理演算子を使用できます。 詳細については、「[グループ化および論理演算子](data-loss-prevention-policies.md#grouping-and-logical-operators)」を参照してください。

![インスタンス数と一致精度のオプション](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a>ラベルの分類子の構成

**分類子** オプションを選択する場合、1 つ以上の組み込み分類子を選択します。

![分類子と機密ラベルのオプション](../media/sensitivity-labels-classifers.png)

それらの分類子の詳細については、「[トレーニング可能な分類子 (プレビュー) の概要](classifier-getting-started-with.md)」を参照してください。

プレビュー期間中は、次のアプリが機密ラベルの分類子をサポートします。

- [Office Insider](https://office.com/insider) の Windows 用 Office 365 ProPlus デスクトップ アプリ:
    - Word
    - Excel
    - PowerPoint

- [SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にする機能 (パブリック プレビュー)](sensitivity-labels-sharepoint-onedrive-files.md) が有効になっている場合の Web アプリ用の Office:
    - Word
    - Excel
    - PowerPoint
    - Outlook

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a>ユーザーが機密ラベルを適用することを推奨

状況に応じて、ユーザーがラベルを適用することを推奨できます。 このオプションでは、分類および関連する保護を受け入れるか、またはラベルがそのコンテンツに適していない場合、推奨事項を無視するかをユーザーが選択できます。

推奨ラベルは、Word、PowerPoint、および Excel でサポートされています。

![機密ラベルをユーザーに推奨するためのオプション](../media/Sensitivity-labels-Recommended-label-option.png)

ラベルを推奨される操作として適用するように条件を構成したときのプロンプトの例を、カスタム ポリシー ヒントと共に示します。ポリシー ヒントに表示するテキストを選択できます。

![推奨ラベルを適用するためのプロンプト](../media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a>自動ラベルと推奨ラベルが適用されるしくみ

- 自動ラベル付けは、Word、Excel、PowerPoint でドキュメントが保存されるときと、Outlook で電子メールが送信されるときに適用されます。 これらの条件により、ドキュメントや電子メール内の本文、およびヘッダーとフッターに含まれる機密情報が検出されますが、件名や電子メールの添付ファイルのものは検知されません。

- 以前に手動でラベルが付けられているか、以前に上位の機密度で自動的にラベルが付けられているドキュメントと電子メールには自動ラベル付けを使用できません。 ドキュメントや電子メールに適用できる機密ラベルは (1 つの保持ラベルに加えて) 1 つだけであることにご注意ください。

- 推奨ラベル付けは、Word、Excel、PowerPoint でドキュメントが保存されるときに適用されます。

- 以前に上位の機密度でラベルが付けられているドキュメントには推奨ラベル付けを使用できません。 コンテンツにすでに上位の機密度でラベルが付けられている場合、推奨事項とポリシー ヒントに関するプロンプトは、ユーザーに表示されません。

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a>複数のラベルに適用するときの複数の条件の評価方法

ラベルは、ポリシー内で指定した位置に従って評価の順序を決められます。先頭に配置したラベルが最下位 (機密性が最も低い) になり、最後に配置したラベルが最上位 (機密性が最も高い) になります。優先度に関する詳細については、「[ラベルの優先度 (順序の問題)](sensitivity-labels.md#label-priority-order-matters)」を参照してください。

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a>自動適用または推奨されるように親ラベルを構成しない

親ラベル (サブラベルのあるラベル) はコンテンツに適用できません。 親ラベルは Azure Information Protection 統合ラベル付けクライアントを使用する Office アプリのコンテンツには適用されないため、決して親ラベルを自動適用または推奨するように構成しないでください。 親ラベルとサブラベルの詳細については、「[サブラベル (ラベルのグループ化)](sensitivity-labels.md#sublabels-grouping-labels)」を参照してください。
