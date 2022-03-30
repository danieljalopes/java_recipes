# Java Stream


## Map to new List of another Object

Map a List of
```Java
Country{
    private String code;
	private String description; 

    public Country(String code, String description){
        this.code = code;
        this.name = description;
    }
}
```

to List of
```Java
CountryDTO{
    private String code;
	private String name;

    public CountryDTO(String code, String name){
        this.code = code;
        this.name = name;
    } 
}
```

Recipe
```Java
List<CountryDTO> countries = new ArrayList<>();
countries.add(new Country("PT", "Portugal"))
countries.add(new Country("BR", "Brazil"))

List<CountryDTO> countryDtoList = countries.stream()
.collect(Collectors.mapping(c -> new CountryDTO(c.getDescription(), c.getCode()), Collectors.toList()));
```

