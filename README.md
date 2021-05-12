#テーブル設計

##users　テーブル

| Column     | Type      | Options          |
| -----------| ----------| -----------------|
| email      | string    | null: false      |
| password   | string    | null: false      |
| name       | string    | null: false      |
| profile    | text      | null: false      |
| occupation | text      | null: false      |
| position   | text      | null: false      |

### Association

- has_many :prototypes
- has_many :comments

##prototypes　テーブル

| Column     | Type      | Options          |
| -----------| ----------| -----------------|
| title      | string    | null: false      |
| each_copy  | text      | null: false      |
| concept    | text      | null: false      |
| user       | reference |                  |
| position   | text      | null: false      |

### Association

- belongs_to :users
- has_many :comments


##comments　テーブル

| Column     | Type      | Options          |
| -----------| ----------| -----------------|
| text       | text      | null: false      |
| user       | reference |                  |
| prototype  | reference |                  |

### Association

- belongs_to :users
- belongs_to :prototypes