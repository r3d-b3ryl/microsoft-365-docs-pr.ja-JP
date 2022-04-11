---
title: テンプレートから DLP ポリシーを作成する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-mar2020
- admindeeplinkCOMPLIANCE
description: この記事では、Office 365に含まれるテンプレートのいずれかを使用して DLP ポリシーを作成する方法について説明します。
ms.openlocfilehash: 3617e1f067f4b29470feedcf7381b41a400887f9
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2022
ms.locfileid: "64759105"
---
# <a name="create-a-dlp-policy-from-a-template"></a>テンプレートから DLP ポリシーを作成する

DLP ポリシーを使用する最も簡単で一般的な方法は、Microsoft 365 コンプライアンス センターに含まれるテンプレートのいずれかを使用することです。 これらのテンプレートの 1 つをそのまま使用することも、組織の特定のコンプライアンス要件を満たすようにルールをカスタマイズすることもできます。

Microsoft 365には、さまざまな一般的な規制とビジネス ポリシーのニーズを満たすのに役立つ 40 を超えるすぐに使用できるテンプレートが含まれています。 参照してください。完全なリストの [ポリシー テンプレート](dlp-policy-reference.md#policy-templates) 。 

テンプレートを微調整するには、既存のルールを変更するか、新しいルールを追加します。 たとえば、ルールに新しい種類の機密情報を追加したり、トリガーの難度を変更するためにルール内のカウントを変えたり、業務上の理由を提供することによってルールのアクションをユーザーが上書きできるようにしたり、通知とインシデント レポートの通知先を変更したりできます。 DLP ポリシー テンプレートは、多くの一般的なコンプライアンス シナリオの柔軟な開始点となります。

カスタム テンプレートを選択することもできます。カスタム テンプレートには既定のルールがなく、組織の特定のコンプライアンス要件を満たすようにゼロから DLP ポリシーを構成します。

## <a name="permissions"></a>アクセス許可

DLP ポリシーを作成するコンプライアンス チームのメンバーは、コンプライアンス センターへのアクセス許可を持っている必要があります。 既定では、テナント管理者は、コンプライアンス担当者や他のユーザーにアクセス権を付与できます。 次の手順を実行します。
  
1. Microsoft 365 でグループを作成して、コンプライアンス責任者をグループに追加します。
    
2. セキュリティ &amp; コンプライアンス センターの [**アクセス許可**] ページで役割グループを作成します。 

3. 役割グループを作成するときに、[ロールの **選択** ] セクションを使用して、役割グループに次のロールを追加します。 **DLP コンプライアンス管理**。
    
4. **メンバーの選択** セクションを使用して、以前に作成した Microsoft 365 グループを役割グループに追加します。

**表示専用 DLP コンプライアンス管理** ロールを使用して、DLP ポリシーと DLP レポートに対する表示専用特権を持つロール グループを作成します。

詳細については、「[Give users access to the Office 365 Security & Compliance Center (Office 365 セキュリティ/コンプライアンス センターへのアクセス権をユーザーに付与する)](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)」を参照してください。
  
これらのアクセス許可は、ポリシーを適用しないように DLP ポリシーを作成して適用するために必要です。

### <a name="roles-and-role-groups-in-preview"></a>プレビュー段階の [役割と役割グループ]

プレビューには、アクセス制御を微調整するためにテストできる役割と役割グループがあります。

プレビュー段階の Microsoft Information Protection (MIP) 役割の一覧を次に示します。 詳細については、「[セキュリティとコンプライアンス センターの役割](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)」を参照してください。

- Information Protection 管理者
- Information Protection アナリスト
- Information Protection 調査員
- Information Protection 閲覧者

プレビュー段階の MIP 役割グループの一覧を次に示します。 詳細については、「[セキュリティとコンプライアンス センターの役割グループ](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#role-groups-in-the-security--compliance-center)」を参照してください。

- 情報保護
- Information Protection レベル
- Information Protection アナリスト
- Information Protection 調査担当者
- Information Protection 閲覧者

### <a name="create-the-dlp-policy-from-a-template"></a>テンプレートから DLP ポリシーを作成する

1. Microsoft 365 コンプライアンス センターにサインイン<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">します</a>。

2. コンプライアンス センター \> の左側のナビゲーション \> **ソリューション** \> **データ損失防止** \> **ポリシー** \> **+ ポリシーの作成**。

    ![ポリシー ボタンを作成します。](../media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
          
3. 必要な種類の機密情報を保護する DLP ポリシー テンプレートを選び、**[次へ]** を選択します。

4. ポリシーの名前を設定し、**[次へ]** を選びます。
 
<!--In this example, you'll select **Privacy** \> **U.S. Personally Identifiable Information (PII) Data** because it already includes most of the types of sensitive information that you want to protect - you'll add a couple later.

    When you select a template, you can read the description on the right to learn what types of sensitive information the template protects.

    ![Page for choosing a DLP policy template.](../media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)-->

5. DLP ポリシーで保護する場所を選択し、場所ごとに既定のスコープを受け入れるか、スコープをカスタマイズします。 スコープ オプションの [場所](dlp-policy-reference.md#locations) を参照してください。

6. [\> **次へ**]を選択します。
 
1. 次のいずれかの操作を行います。

   - **[Office 365 のすべての場所]** \> **[次へ]** と選びます。
   - **[自分で特定の場所を選択する]** \> **[次へ]** と選びます。この例では、これを選びます。

   すべての Exchange メールやすべての OneDrive アカウントなど、特定の場所全体を含めたり除外したりするには、その場所の **[状態]** をオンまたはオフに切り替えます。

   特定の SharePoint サイトまたは OneDrive for Business アカウントだけを含めるには、**[状態]** をオンに切り替えた後、**[含める]** の下のリンクをクリックして、特定のサイトまたはアカウントを選びます。ポリシーをサイトに適用すると、そのポリシーに構成されたルールがそのサイトのすべてのサブサイトに自動的に適用されます。

   ![DLP ポリシーを適用できる場所のオプション。](../media/all-locations.png)

   この例では、すべての OneDrive for Business アカウントに保存されている機密情報を保護するために、**Exchange メール** と **SharePoint サイト** の両方の **[状態]** をオフにし、**OneDrive アカウント** の **[状態]** はそのままにします。

7. テンプレート \> [**次へ**] **から [校閲] を選択し、既定の設定をカスタマイズします**。

8. DLP ポリシー テンプレートには、条件付きの定義済みルールと、特定の種類の機密情報を検出して適用するアクションが含まれています。既存のルールのいずれかを編集、削除、またはオフにするか、新しいルールを追加できます。完了したら、**[次へ]** をクリックします。

    ![米国 PII ポリシー テンプレートで展開されたルール。](../media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)

9. 次のいずれかの場所を選択した場合、このコンテンツが組織内または組織外でいつ共有されているかを検出することを選択します。
    1. Exchange
    1. SharePoint
    1. OneDrive
    1. チャット メッセージとチャネル メッセージをTeamsする 

10. [**次へ**]を選択します。

11. 必要に応じて、[ **保護アクション]** ページで、ポリシー ヒント通知と通知メールをカスタマイズできます。 **コンテンツがポリシー条件と一致する場合に有効にし、ポリシーのヒントをユーザーに表示し、電子メール通知を送信** してから、[**ヒントと電子メールのカスタマイズ**] を選択します。
12. [ **次へ**] を選びます。


<!--    In this example, the U.S. PII Data template includes two predefined rules:

   - **Low volume of content detected U.S. PII** This rule looks for files containing between 1 and 10 occurrences of each of three types of sensitive information (ITIN, SSN, and U.S. passport numbers), where the files are shared with people outside the organization. If found, the rule sends an email notification to the primary site collection administrator, document owner, and person who last modified the document.

   - **High volume of content detected U.S. PII** This rule looks for files containing 10 or more occurrences of each of the same three sensitive information types, where the files are shared with people outside the organization. If found, this action also sends an email notification, plus it restricts access to the file. For content in a OneDrive for Business account, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.

    To meet your organization's specific requirements, you may want to make the rules easier to trigger, so that a single occurrence of sensitive information is enough to block access for external users. After looking at these rules, you understand that you don't need low and high count rules—you need only a single rule that blocks access if any occurrence of sensitive information is found.

    So you expand the rule named **Low volume of content detected U.S. PII** \> **Delete rule**.

    ![Delete rule button.](../media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)

9. Now, in this example, you need to add two sensitive information types (U.S. bank account numbers and U.S. driver's license numbers), allow people to override a rule, and change the count to any occurrence. You can do all of this by editing one rule, so select **High volume of content detected U.S. PII** \> **Edit rule**.

    ![Edit rule button.](../media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)

10. To add a sensitive information type, in the **Conditions** section \> **Add or change types**. Then, under **Add or change types** \> choose **Add** \> select **U.S. Bank Account Number** and **U.S. Driver's License Number** \> **Add** \> **Done**.

    ![Option to Add or change types.](../media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)

    ![Add or change types pane.](../media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)

11. To change the count (the number of instances of sensitive information required to trigger the rule), under **Instance count** \> choose the **min** value for each type \> enter 1. The minimum count cannot be empty. The maximum count can be empty; an empty **max** value convert to **any**.

    When finished, the min count for all of the sensitive information types should be **1** and the max count should be **any**. In other words, any occurrence of this type of sensitive information will satisfy this condition.

    ![Instance counts for sensitive information types.](../media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)

12. For the final customization, you don't want your DLP policies to block people from doing their work when they have a valid business justification or encounter a false positive, so you want the user notification to include options to override the blocking action.

    In the **User notifications** section, you can see that email notifications and policy tips are turned on by default for this rule in the template.

    In the **User overrides** section, you can see that overrides for a business justification are turned on, but overrides to report false positives are not. Choose **Override the rule automatically if they report it as a false positive**.

    ![User notifications section and User overrides section.](../media/62720e7a-a939-4c03-b414-67748f3d64a0.png)

13. At the top of the rule editor, change the name of this rule from the default **High volume of content detected U.S. PII** to **Any content detected with U.S. PII** because it's now triggered by any occurrence of its sensitive information types.

14. At the bottom of the rule editor \> **Save**.

15. Review the conditions and actions for this rule \> **Next**.

    On the right, notice the **Status** switch for the rule. If you turn off an entire policy, all rules contained in the policy are also turned off. However, here you can turn off a specific rule without turning off the entire policy. This can be useful when you need to investigate a rule that is generating a large number of false positives.

16. On the next page, read and understand the following, and then choose whether to turn on the rule or test it out first \> **Next**.

     Before you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before you fully enforce them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require to get their work done.

    If you're creating DLP policies with a large potential impact, we recommend following this sequence:

17. Start in test mode without Policy Tips and then use the DLP reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization.

18. Move to Test mode with notifications and Policy Tips so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.

19. Turn on the policies so that the rules are enforced and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.

    ![Options for using test mode and turning on policy.](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

20. Review your settings for this policy \> choose **Create**.

After you create and turn on a DLP policy, it's deployed to any content sources that it includes, such as SharePoint Online sites or OneDrive for Business accounts, where the policy begins automatically enforcing its rules on that content.


## Example: Identify sensitive information across all OneDrive for Business sites and restrict access for people outside your organization

OneDrive for Business accounts make it easy for people across your organization to collaborate and share documents. But a common concern for compliance officers is that sensitive information stored in OneDrive for Business accounts may be inadvertently shared with people outside your organization. A DLP policy can help mitigate this risk.

In this example, you'll create a DLP policy that identifies U.S. PII data, which includes Individual Taxpayer Identification Numbers (ITIN), Social Security Numbers, and U.S. passport numbers. You'll get started by using a template, and then you'll modify the template to meet your organization's compliance requirements—specifically, you'll:

- Add a couple of types of sensitive information—U.S. bank account numbers and U.S. driver's license numbers—so that the DLP policy protects even more of your sensitive data.

- Make the policy more sensitive, so that a single occurrence of sensitive information is enough to restrict access for external users.

- Allow users to override the actions by providing a business justification or reporting a false positive. This way, your DLP policy won't prevent people in your organization from getting their work done, provided they have a valid business reason for sharing the sensitive information.


## View the status of a DLP policy

At any time, you can view the status of your DLP policies on the **Policy** page in the **Data loss prevention** section of the Security &amp; Compliance Center. Here you can find important information, such as whether a policy was successfully enabled or disabled, or whether the policy is in test mode.

Here are the different statuses and what they mean.

<br>

****

|Status|Explanation|
|---|---|
|**Turning on...**|The policy is being deployed to the content sources that it includes. The policy is not yet enforced on all sources.|
|**Testing, with notifications**|The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are sent to the specified recipients.|
|**Testing, without notifications**|The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are not sent to the specified recipients.|
|**On**|The policy is active and enforced. The policy was successfully deployed to all its content sources.|
|**Turning off...**|The policy is being removed from the content sources that it includes. The policy may still be active and enforced on some sources. Turning off a policy may take up to 45 minutes.|
|**Off**|The policy is not active and not enforced. The settings for the policy (sources, keywords, duration, etc) are saved.|
|**Deleting...**|The policy is in the process of being deleted. The policy is not active and not enforced. It normally takes an hour for a policy to delete.|
|

## Turn off a DLP policy

You can edit or turn off a DLP policy at any time. Turning off a policy disables all of the rules in the policy.

To edit or turn off a DLP policy, on the **Policy** page \> select the policy \> **Edit policy**.

![Edit policy button.](../media/ce319e92-0519-44fe-9507-45a409eaefe4.png)

In addition, you can turn off each rule individually by editing the policy and then toggling off the **Status** of that rule, as described above.

## More information

- [Learn about data loss prevention](dlp-learn-about-dlp.md)
- [Send notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md)
- [Create a DLP policy to protect documents with FCI or other properties](protect-documents-that-have-fci-or-other-properties.md)
- [What the DLP policy templates include](what-the-dlp-policy-templates-include.md)
- [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)
