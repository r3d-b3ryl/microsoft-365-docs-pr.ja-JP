---
title: パスワード ポリシーの推奨事項
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: パスワード攻撃に対する組織のセキュリティを強化し、一般的なパスワードを禁止し、リスク ベースの多要素認証を有効にします。
ms.openlocfilehash: bf722e665950be87ed652f4df7fa7e5b2298959c
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391329"
---
# <a name="password-policy-recommendations"></a>パスワード ポリシーの推奨事項

組織の管理者は、組織内のユーザー向けのパスワード ポリシーを設定する必要があります。パスワード ポリシーの設定は複雑でわかりにくい場合があります。この記事では、パスワード攻撃からの組織の保護を強化するための推奨事項を示します。
  
組織で Microsoft 365 パスワードが期限切れとなる頻度を決める場合は、「[Microsoft 365 のパスワード有効期限ポリシーを設定する](../manage/set-password-expiration-policy.md)」を参照してください。

Microsoft 365 パスワードの詳細については、以下を参照してください。

[パスワードをリセットする](../add-users/reset-passwords.md) (記事)

[個別のユーザーのパスワードを無期限に設定する](../add-users/set-password-to-never-expire.md) (記事)

[ユーザーが自分でパスワードをリセットできるようにする](../add-users/let-users-reset-passwords.md) (記事)

[ユーザーのパスワードを再送信する - 管理者向けヘルプ](../add-users/resend-user-password.md) (記事)
  
## <a name="understanding-password-recommendations"></a>パスワードの推奨事項について

適切なパスワード手法は、次のようないくつかのカテゴリに大きく分けられます。
  
- **一般的な攻撃に対抗する** これは、ユーザーがパスワードを入力する場所 (マルウェアを適切に検出できる既知の信頼できるデバイス、検証済みサイト) の選択、およびパスワード (長さと一意性) の選択に関係します。

- **成功した攻撃を含める** 成功したハッカーの攻撃を含めるのは、特定のサービスへの公開を制限するためです。また、ユーザーのパスワードが盗まれた場合に、その損害を完全に防ぐことにもなります。たとえば、ソーシャル ネットワーク資格情報の侵害により、銀行口座が攻撃を受けやすくならないようにしたり、十分に保護されていないアカウントで重要なアカウントのリセット リンクが受け入れられないようにしたりします。

- **人間の性質を理解する** 多くの有効なパスワード手法では、自然な人間の行動には十分対応できません。調査により、ユーザーに適用されるほとんどすべてのルールはパスワードの品質を弱化することがわかっているため、人間の性質を理解することが重要です。長さの要件、特殊文字の要件、パスワード変更の要件はすべて、パスワードを正規化することになるため、攻撃者はパスワードを簡単に推測したり、解読したりすることができるようになります。

## <a name="password-guidelines-for-administrators"></a>管理者向けのパスワード ガイドライン

より安全なパスワード システムの最大の目的は、パスワードの多様性です。パスワードを推測しにくくするためのパスワード ポリシーが必要です。組織を可能な限り安全な状態に保つための推奨事項をいくつか以下に示します。
  
- 8 桁の最小長要件を維持する

- 文字構成の要件を求めない。たとえば、\*&amp;(^%$ などです。

- ユーザー アカウントの必須の定期的なパスワード リセットを求めない

- 最も脆弱なパスワードがシステムで使用されないように、よく使われるパスワードを禁止する

- 業務以外の目的で組織のパスワードを再利用しないようにユーザーを教育する

- 
            [多要素認証](../security-and-compliance/set-up-multi-factor-authentication.md)の登録を適用する

- リスク ベースの多要素認証チャレンジを有効にする

### <a name="password-guidance-for-your-users"></a>ユーザー向けパスワード ガイダンス

組織内のユーザー向けパスワード ガイダンスをいくつか以下に示します。ユーザーに以下の推奨事項を認識してもらい、組織レベルで推奨されるパスワード ポリシーを適用するようにしてください。
  
- 他の Web サイトで使用しているものと同じ、または似たようなパスワードは使用しない

- 1 単語 (たとえば、 **password** や、 **Iloveyou** などのよく使われるフレーズ) は使用しない

- 友だちと家族の名前と誕生日、お気に入りのバンド、使用しそうなフレーズなど、自分のことをよく知る人でもパスワードを簡単に推測できないようにする

## <a name="some-common-approaches-and-their-negative-impacts"></a>一般的ないくつかの方法とその悪影響

以下は最もよく使われるパスワードの管理手法の一部ですが、調査ではその悪影響について警告しています。
  
### <a name="password-expiration-requirements-for-users"></a>ユーザー向けパスワードの有効期限の要件

パスワードの有効期限の要件にはメリットもありますがデメリットのほうが多くなります。これらの要件に従うと、ユーザーは互いに密接に関係している一連の単語と数字で構成される、予測可能なパスワードを選択することになるためです。このような場合、次のパスワードは前のパスワードに基づいて予測することができます。パスワードの有効期限の要件に抑制効果はありません。サイバー犯罪者は、ほとんどの場合、資格情報を侵害するとすぐに使用するためです。詳しくは、「[必須パスワードの変更を再検討する時間](https://go.microsoft.com/fwlink/p/?linkid=861018)」をご覧ください。
  
### <a name="requiring-long-passwords"></a>長いパスワードを要求する

パスワードの長さ要件 (約 10 文字を超える) により、ユーザーの行動が予測可能で望ましくないものとなる可能性があります。たとえば、16 文字のパスワードを使用するよう求められたユーザーは、文字の長さ要件を満たすものの、推測しにくいものではない **fourfourfourfour** や **passwordpassword** などの繰り返しパターンを選ぶ可能性があります。さらに、長さ要件は、ユーザーがパスワードを書き留めたり、ドキュメントに暗号化されていないパスワードを保存するなど、他の安全でない手法を採用する機会を増やすことになります。ユーザーが一意のパスワードを考えるように、適切な 8 文字の最小長要件を維持することをお勧めします。
  
### <a name="requiring-the-use-of-multiple-character-sets"></a>複数の文字セットの使用を要求する

パスワードの複雑さ要件により、キー スペースが減り、ユーザーが予測可能な方法で行動することになり、これでは元も子もありません。ほとんどのシステムでは、ある程度のパスワードの複雑さ要件を適用します。たとえば、パスワードには、次のカテゴリの 3 つすべての文字が必要となります。
  
- 大文字

- 小文字

- 英数字以外の文字

ほとんどのユーザーは似たようなパターンを使用します。たとえば、最初の位置が大文字、最後が記号、最後の 2 つが数字などです。サイバー犯罪者はこれを認識しているため、最も一般的な置換文字、つまり、"s" の場合は "$"、"a" の場合は "@"、"l" の場合は "1" を使用して辞書攻撃を実行します。ユーザーに大文字、小文字、数字、特殊文字の組み合わせを選択させるのは逆効果です。複雑さ要件によっては、セキュリティで保護された覚えやすいパスワードをユーザーが使用できないようにするものもあり、ユーザーにセキュリティ レベルの低い覚えにくいパスワードを思い付かせることになります。
  
## <a name="successful-patterns"></a>成功パターン

上記のものとは対照的に、パスワードに多様性を持たせる推奨事項をいくつか以下に示します。
  
### <a name="ban-common-passwords"></a>よく使われるパスワードを禁止する

パスワードを作成するときにユーザーに認識させる最も重要なパスワード要件は、パスワードの総当たり攻撃に対する組織の脆弱性を軽減するために、よく使われるパスワードの使用を禁止することです。よく使われるユーザー パスワードには、 **abdcefg**、**password**、**monkey** などがあります。
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a>組織のパスワードを他の場所で再利用しないようにユーザーを教育する

組織内のユーザーに伝える最も重要なメッセージの 1 つは、組織のパスワードを他の場所で再利用しないということです。外部の Web サイトで組織のパスワードを使用すると、サイバー犯罪者がこれらのパスワードを侵害する可能性が高くなります。
  
### <a name="enforce-multi-factor-authentication-registration"></a>多要素認証の登録を適用する

ユーザーが、代替メール アドレス、電話番号、プッシュ通知用に登録されたデバイスなどの連絡先とセキュリティ情報を更新し、セキュリティ チャレンジに応答して、セキュリティ イベントに関する通知を受け取れるようにします。更新された連絡先とセキュリティ情報は、ユーザーが万が一パスワードを忘れてしまった場合、または他のユーザーがアカウントを引き継ごうとした場合の本人確認に役立ちます。また、ログイン試行やパスワード変更など、セキュリティ イベントが発生した場合には、帯域外の通知チャネルが提供されます。 
  
詳細については、「[Office 365 ユーザー用の多要素認証を設定する](../security-and-compliance/set-up-multi-factor-authentication.md)」を参照してください。
  
### <a name="enable-risk-based-multi-factor-authentication"></a>リスク ベースの多要素認証を有効にする

リスク ベースの多要素認証では、Microsoft のシステムで不審な動作が検出されたときに、正当なアカウント所有者であることを確認するためにユーザーに対してチャレンジを実行することができます。 
  
## <a name="next-steps"></a>次の手順

パスワードの管理についてさらに詳しい情報が必要な場合は、 以下でおすすめの記事をお読みください:

- [パスワードは忘れて、これからはパスワードレス](https://www.microsoft.com/security/business/identity-access-management/passwordless-authentication)

- [Microsoft パスワード ガイダンス](https://www.microsoft.com/research/wp-content/uploads/2016/06/Microsoft_Password_Guidance-1.pdf)

- [Do Strong Web Passwords Accomplish Anything?](https://go.microsoft.com/fwlink/p/?linkid=861008) (強力な Web パスワードでできること)

- [Password Portfolios and the Finite-Effort User](https://go.microsoft.com/fwlink/p/?linkid=861014) (パスワード ポートフォリオとユーザーの有限労力)

- [Preventing Weak Passwords by Reading Users' Minds](https://go.microsoft.com/fwlink/p/?linkid=861015) (ユーザーの心を読み取り、脆弱なパスワードの使用を防ぐ)

- [Choosing Secure Passwords](https://go.microsoft.com/fwlink/p/?linkid=861016) (セキュリティで保護されたパスワードの選択)

- [Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018) (必須パスワードの変更を再検討する時間)

- [Worst Passwords of 2015](https://go.microsoft.com/fwlink/p/?linkid=861020) (2015 年のワースト パスワード)

## <a name="related-content"></a>関連コンテンツ

[パスワードをリセットする](../add-users/reset-passwords.md) (記事)\
[個別のユーザーのパスワードを無期限に設定する](../add-users/set-password-to-never-expire.md) (記事)\
[ユーザーが自分でパスワードをリセットできるようにする](../add-users/let-users-reset-passwords.md) (記事)\
[ユーザーのパスワードを再送信する - 管理者向けヘルプ](../add-users/resend-user-password.md) (記事)
